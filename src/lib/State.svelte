<script lang="ts">
  // dalam svelte terdapat istilah rune yang digunakan sebagai pengontrol svelte compiler
  // rune memiliki simbol awalan -> $
  // contoh penggunaan rune (state) -> $state(parameter)
  // sekilas dari yang terlihat seperti sebuah function atau method

  // reactive state adalah salah satu dari implementasi rune
  // reactive state adalah state yang dapat merender ulang tampilan ketika state tersebut berubah
  // perbedaan dengan state biasa adalah state biasa tidak dapat merender ulang tampilan ketika state tersebut berubah

  // contoh implementasi tanpa menggunakan reactive state

  let hitungs: number = 0;

  function increment() {
    hitungs++;
    document.getElementById('hitung').innerText = 'Jumlah : ' + hitungs;
  }

  let state: number = $state(0);

  function hitung() {
    return state++;
  }

  let warnaFont = $state('text-black');

  function gantiWarnaMerah() {
    warnaFont = 'text-red-500';
  }

  function gantiWarnaHijau() {
    warnaFont = 'text-green-500';
  }

  function gantiWarnaBiru() {
    warnaFont = 'text-blue-500';
  }
</script>

<p id="hitung">Jumlah : 0</p>

<button onclick={increment}> hitung </button> <br />
<button onclick={hitung}>
  {state}
</button>

<!-- button merah -->
<button
  class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded"
  onclick={gantiWarnaMerah}>Merah</button>

<!-- button hijau -->
<button
  class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded"
  onclick={gantiWarnaHijau}>Hijau</button>

<!-- button biru -->
<button
  class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
  onclick={gantiWarnaBiru}>Biru</button>

<p class={warnaFont}>
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam,
  voluptatibus.
</p>
