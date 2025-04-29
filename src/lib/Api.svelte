<script lang="ts">
  import {Button} from './components/ui/button';

  const apiUrl: string = 'https://valorant-api.com/v1/agents';

  let data: any = $state([]);

  const fetchData = async () => {
    try {
      const response = await fetch(apiUrl);
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
      }
      const result = await response.json();
      data = result.data;
      console.log(data);
      alert('Data fetched successfully!');
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  };
</script>

<Button
  onclick={fetchData}
  class="bg-green-600 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
  Fetch Data
</Button>

<!-- menampilkan data -->
{#if data.length > 0}
  <div class="grid grid-cols-3 gap-4">
    {#each data as item}
      <div class="bg-white shadow-md rounded-lg p-4">
        <h2 class="text-xl font-bold">{item.displayName}</h2>
        <img
            loading="lazy"
          src={item.fullPortrait}
          alt={item.displayName}
          class="w-full h-auto rounded-lg" />
        <p>{item.description}</p>
      </div>
    {/each}
  </div>
{/if}
