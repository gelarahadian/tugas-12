<template>
    <div class="card">
        <h2>Masukan Data Siswa</h2>
        <form @submit.prevent="addTask() " class="card-body"> 
            <div class="form-group">
                <label for="nik">NIK:</label>
                <div>
                    <input class="form-control" type="text" name="nik" id="nik" v-model="newSiswa.nik"/>
                </div>
            </div>
            <div>
                <label for="nama">Nama:</label>
                <div>
                <input class="form-control" type="text" name="nama" id="nama" v-model="newSiswa.nama"/>
                </div>
            </div>
            <div>
                <label for="nilai">Nilai:</label>
                <div>
                <input class="form-control" type="text" name="nilai" id="nilai" v-model="newSiswa.nilai"/>
                </div>
            </div>
            <div class="mt-3">  
                <button class="btn btn-primary" type="submit">Submit</button>            </div>
        </form>
    </div>
</template>

<script>
export default {
    props: {
        lengthSiswa: Number
    },
    emits: ['addTask'],
    data() {
        return{
            newSiswa: {
                nik: '',
                nama: '',
                nilai: ''
            }
        }
    },
    methods: {
        addTask() {
            this.$emit('addTask', {
                id: this.lengthSiswa + 1,
                ...this.newSiswa});
            this.newSiswa = {
                nik: '',
                nama: '',
                nilai: ''
            }
        }
    }
}
</script>