<template>
  <div class="container">
    <h1>Nilai Tugas Siswa</h1>
    <DaftarSiswa  :daftarSiswa="daftarSiswa"
     />
     <h3>Rata rata Nilai Semua Siswa: {{rataRataNilai}}</h3>
    <Form 
    @addTask="handleAddTask"
    :lengthSiswa="daftarSiswa.length" />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      daftarSiswa: []
    }
  },
  methods: {
    handleAddTask(value) {
      this.daftarSiswa.push(value)
    }
  },
  computed: {
    rataRataNilai() {
      let nilaiSiswa = []
      if( this.daftarSiswa.length === 0) {
        return 0
      }
      this.daftarSiswa.map((siswa) => {
        nilaiSiswa.push(parseInt(siswa.nilai))
      })
      const jumlahNilai = nilaiSiswa.reduce((total, nilai) => {
        return total + nilai
      }) 
      const rataRata = jumlahNilai / this.daftarSiswa.length
      return rataRata
    }
  }
  
  
}
</script>
