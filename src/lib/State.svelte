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
</script>

<p id="hitung">Jumlah : 0</p>

<button onclick={increment}> hitung </button> <br />

<button onclick={hitung}>
  {state}
</button>
