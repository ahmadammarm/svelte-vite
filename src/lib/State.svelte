<script lang="ts">
  // dalam svelte terdapat istilah rune yang digunakan sebagai pengontrol svelte compiler
  // rune memiliki simbol awalan -> $
  // contoh penggunaan rune (reactive state) -> $state(parameter)
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

  //   contoh implementasi dengan menggunakan reactive state
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
  let angka1: number = $state(0);
  let angka2: number = $state(0);
  let hasil: number = $state(0);

  function tambah() {
    hasil = angka1 + angka2;
  }

  function kurang() {
    hasil = angka1 - angka2;
  }

  let nama: string = $state('');

  function gantiNama() {
    if (nama == '') {
      nama = 'Ammar';
    }
  }

  let warna = $state('');
  let hasilWarna = $state('');

  function gantiWarnaFont() {
    if (warna == 'merah' || warna == 'red') {
      hasilWarna = 'text-red-500';
    } else if (warna == 'hijau' || warna == 'green') {
      hasilWarna = 'text-green-500';
    } else if (warna == 'biru' || warna == 'blue') {
      hasilWarna = 'text-blue-500';
    } else if (warna == 'hitam' || warna == 'black') {
      hasilWarna = 'text-black';
    } else {
      alert('Warna tidak valid');
    }
  }
</script>

<p class={`${hasilWarna} text-2xl font-bold`}>Ammar</p>

<input type="text" bind:value={warna} placeholder="Masukkan warna" />

<button
  class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
  onclick={gantiWarnaFont}>
  Ganti warna
</button>

<input type="number" bind:value={angka1} placeholder="Masukkan angka pertama" />
<input type="number" bind:value={angka2} placeholder="Masukkan angka kedua" />
<button onclick={tambah}>Tambah</button>
<button onclick={kurang}>Kurang</button>

<p>
  Hasil : {hasil}
</p>

<p>Hello, {nama}</p>
<button onclick={gantiNama}>Ganti Nama</button>

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
