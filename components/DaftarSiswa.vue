<template>
<table class="table">
  <thead>
    <tr>
      <th scope="col">NO</th>
      <th scope="col">NIK</th>
      <th scope="col">Name</th>
      <th scope="col">Nilai</th>
    </tr>
  </thead>
  <tbody>
    <Siswa v-for="siswa of daftarSiswa" 
        :key="siswa.id" :siswa="siswa"/>
  </tbody>
</table>
</template>

<script>
export default {
    props: {
        daftarSiswa: Array
    },
    
}
</script>