<script>
    let data;
  
    async function fetchData() {
      const response = await fetch('http://166.104.191.253:8089/academyinfo?year=2023');
      data = await response.json();
    }
  
    fetchData();
  </script>
  
  <h1>Data:</h1>
  {#if data}
    <ul>
      {#each data as item}
        <li>{item.학교명} 외국인학생수 : {item.외국인학생수}</li>
      {/each}
    </ul>
  {:else}
    <p>Loading...</p>
  {/if}
  