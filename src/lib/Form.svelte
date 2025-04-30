<script lang="ts">
    let inputanWarna: string = $state('');
    let hasilWarna: string = $state('')

    const gantiWarna = () => {
        inputanWarna = document.getElementById('inputanWarna').value;

        if(inputanWarna == "merah" || inputanWarna == "red") {
            hasilWarna = "text-red-500";
        } else if(inputanWarna == "hijau" || inputanWarna == "green") {
            hasilWarna = "text-green-500";
        } else if(inputanWarna == "biru" || inputanWarna == "blue") {
            hasilWarna = "text-blue-500";
        } else if(inputanWarna == "hitam" || inputanWarna == "black") {
            hasilWarna = "text-black";
        } else {
            alert("Warna tidak valid");
        }
    }
</script>

<input type="text" id="inputanWarna" placeholder="Masukkan warna" />
<button onclick={gantiWarna}>Ganti Warna</button>

<p class={`${hasilWarna}`}>ammar</p>