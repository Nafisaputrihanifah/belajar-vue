<template>
  <div>
    <h2>Formulir</h2>
    <form @submit.prevent="submitForm">
      <label for="">Nama</label>
      <input class="{'is-invalid':isInvalidName}"
       type="text" name="nama" v-model="kontak.nama">
       <div v-if="isInvalidName" class="error-message">
        Nama harus disi
       </div>
      <br>
      <label for="">Kelas</label>
      <input class="{'is-invalid':isInvalidKelas}" 
      type="text" name="kelas" v-model="kontak.kelas">
      <div v-if="isInvalidKelas" class="error-message">
        Kelas harus disi 
       </div>
      <br>
      <label for="">Alamat</label>
      <input class="{'is-invalid':isInvalidAlamat}" 
      type="text" name="alamat" v-model="kontak.alamat">
      <div v-if="isInvalidAlamat" class="error-message">
        Alamat harus disi 
       </div>
      <br>
      <label for="">Nilai Matematika</label>
      <input class="{'is-invalid':isInvalidNilaimtk}" 
      type="text" name="nilaimtk" v-model="kontak.nilaimtk">
      <div v-if="isInvalidNilaimtk" class="error-message">
        Nilai Matematika harus disi 
       </div>
      <br>
      <label for="">Nilai Bahasa Indonesia</label>
      <input class="{'is-invalid':isInvalidNilaibindo}" 
      type="text" name="nilai" v-model="kontak.nilaibindo">
      <div v-if="isInvalidNilaibindo" class="error-message">
        Nilai Bahasa Indonesia harus disi 
       </div>
      <br>
      <label for="">Nilai IPA</label>
      <input class="{'is-invalid':isInvalidNilaiipa}" 
      type="text" name="nilai" v-model="kontak.nilaiipa">
      <div v-if="isInvalidNilaiipa" class="error-message">
        Nilai ipa harus disi 
       </div>
      <br>
      <button type="submit">Simpan</button>
    </form>
    <div v-if="showResult">
      nama : {{ name }} <br>
      kelas : {{ kelas }} <br>
      alamat : {{ alamat }} <br>
      nilaimtk : {{ nilaimtk }} <br>
      nilaibindo : {{ nilaibindo }} <br>
      nilaiipa : {{ nilaiipa }} <br>
      total : {{ total }} <br>
      keterangan: {{ keterangan }}
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  data() {
    return {
      kontak: {
        nama: '',
        kelas: '',
        alamat : '',
        nilaimtk : '',
        nilaibindo : '',
        nilaiipa: '',
        total: '',
        keterangan: '',
      },
      showResult: ref(false),
      name: ref(''),
      kelas: ref(''),
      alamat: ref(''),
      nilaimtk: ref(''),
      nilaibindo:ref(''),
      nilaiipa :ref( ''),
      total: 0,
      keterangan: ref('')
    };
  },
  computed: {
    isInvalidName(){
      return this.name.length <= 1;

    },
    isInvalidKelas(){
      return this.kelas.length <= 1;
    },
    isInvalidAlamat(){
      return this.alamat.length <= 1;
    },
    isInvalidNilaimtk(){
      return this.nilaimtk.length <= 1;
    },
    isInvalidNilaibindo(){
      return this.nilaibindo.length <= 1;
    },
    isInvalidNilaiipa(){
      return this.nilaiipa.length <= 1;
    },
  },
  methods: {
    submitForm() {
      this.name = this.kontak.nama;
      this.kelas = this.kontak.kelas;
      this.alamat = this.kontak.alamat;
      this.nilaimtk = this.kontak.nilaimtk;
      this.nilaibindo = this.kontak.nilaibindo;
      this.nilaiipa = this.kontak.nilaiipa;
      if(this.total > 240){
        this.keterangan = "Lulus"
      }else{
        this.keterangan = "Tidak Lulus"
      }
      this.total = parseInt(this.nilaimtk) + parseInt(this.nilaibindo) + parseInt(this.nilaiipa);
      this.showResult = true;
      this.isInvalidName = false;
      this.isInvalidKelas = false;
      this.isInvalidAlamat = false;
      this.isInvalidNilaimtk = false;
      this.isInvalidNilaibindo = false;
      this.isInvalidNilaiipa= false;


    },
  },
};
</script>

<style>
h2 {
  color: blue;
}

.error-message {
  color: red;
  margin-top: 5px;
}

.is-invalid{
  border-color: red;
}
</style>