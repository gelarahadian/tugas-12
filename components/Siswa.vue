<template>
    <tr>
      <th scope="row">{{siswa.id}}</th>
      <td>{{siswa.nik}}</td>
      <td>{{siswa.nama}}</td>
      <td>{{siswa.nilai}}</td>
    </tr>
</template>

<script>
export default {
    props: {
        siswa: Object
    }
}
</script>