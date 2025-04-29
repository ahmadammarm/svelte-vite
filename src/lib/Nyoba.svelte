<script lang="ts">
  const content: string = "<h1 class='font-bold'>Hello World</h1>";
</script>

<!-- tag html digunakan untuk merender value yang berisikan kode html -->
<!-- misalnya pada kode diatas kita memiliki variable content dengan tipe string yang berisikan format html -->
<!-- dengan menuliskan tag html, maka content tersebut akan mengabaikan tag h1 untuk dirender dan berubah menjadi h1 biasa dalam tampilan -->
<!-- kita juga bisa menambahkan class atau atribut yang lain juga dalam value tersebut -->
{@html content}
