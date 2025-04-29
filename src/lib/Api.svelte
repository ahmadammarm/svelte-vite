<script lang="ts">
    import { Button } from "./components/ui/button";


    const apiUrl: string = "https://valorant-api.com/v1/agents";

    const fetchData = async () => {
        try {
            const response = await fetch(apiUrl);
            if (!response.ok) {
                throw new Error(`HTTP error! status: ${response.status}`);
            }
            const data = await response.json();
            console.log(data);
            alert("Data fetched successfully!");
        } catch (error) {
            console.error("Error fetching data:", error);
        }
    }

</script>

<Button onclick={fetchData} class="bg-green-600 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
    Fetch Data
</Button>