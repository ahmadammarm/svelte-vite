<script lang="ts">

    // derived state adalah state yang dihasilkan dari state lain
    // misalkan

    let hitung = $state(0);
    let kali = $derived(hitung * 3);

    // jika state hitung berubah maka state kali yang merupakan derived state juga akan berubah

</script>

<button onclick={function() { hitung++; }}>
    {kali}
</button>

<p>
    jika angka {hitung} dikali 3 maka hasilnya adalah {kali}``
</p>
