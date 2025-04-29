<script lang="ts">
    // dalam svelte terdapat istilah rune yang digunakan sebagai pengontrol svelte compiler
    // rune memiliki simbol awalan -> $
    // contoh penggunaan rune (state) -> $state(parameter)
    // sekilas dari yang terlihat seperti sebuah function atau method

    let state: number = $state(0)

    function hitung() {
        return state++
    }

</script>

<button onclick={hitung}>
    {state}
</button>