<template>
  <div id="app">
    <div id="hero">
        <div id="hero-overlay">
          <div class="container">
            <div class="row">
              <div class="col-sm-8 offset-sm-2 mt-3">
                <h1 class="text-center">Form Mahasiswa</h1>
                  <form class="mt-3" @submit="handleRegister">
                      <div class="form-group row">
                        <label for="inputnim" class="col-sm-4 col-form-label">NIM</label>
                        <div class="col-sm-8" id="colnim">
                          <input type="text" v-model="nim" @keyup="nimEvent" class="form-control" id="inputnim" placeholder="NIM">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputname" class="col-sm-4 col-form-label">Nama Mahasiswa</label>
                        <div class="col-sm-8" id="colname">
                          <input type="text" v-model="name" @keyup="nameEvent" class="form-control" id="inputname" placeholder="Nama Mahasiswa">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputkelas" class="col-sm-4 col-form-label">Kelas</label>
                        <div class="col-sm-8" id="colkelas">
                          <input type="text" v-model="kelas" @keyup="kelasEvent" class="form-control" id="inputkelas" placeholder="Kelas">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputjurusan" class="col-sm-4 col-form-label">Jurusan</label>
                        <div class="col-sm-8" id="coljurusan">
                          <input type="text" v-model="jurusan" @keyup="jurusanEvent" class="form-control" id="inputjurusan" placeholder="Jurusan">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputskripsi" class="col-sm-4 col-form-label">Judul Skripsi</label>
                        <div class="col-sm-8" id="colskripsi">
                          <input type="text" v-model="skripsi" @keyup="skripsiEvent" class="form-control" id="inputskripsi" placeholder="Judul Skripsi">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputtanggal" class="col-sm-4 col-form-label">Tanggal</label>
                        <div class="col-sm-4" id="coltanggal">
                          <input type="date" v-model="tanggal" @keyup="tanggalEvent" class="form-control" id="inputtanggal" placeholder="Tanggal">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputjam" class="col-sm-4 col-form-label">Jam</label>
                        <div class="col-sm-3" id="coljam">
                          <input type="time" v-model="jam" @keyup="jamEvent" class="form-control" id="inputjam" placeholder="Jam">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputemail" class="col-sm-4 col-form-label">Email</label>
                        <div class="col-sm-8" id="colemail">
                          <input type="email" v-model="email" @keyup="emailEvent" class="form-control" id="inputemail" placeholder="Email">
                        </div>
                      </div>
                      <div class="form-group row">
                        <label for="inputmateri" class="col-sm-4 col-form-label">Materi Bimbingan</label>
                        <div class="col-sm-8" id="colmateri">
                          <textarea name="deskripsi" v-model="materi" class="form-control" @keyup="materiEvent" id="materi" cols="65" rows="3" placeholder="Masukkan Deskripsi Bimbingan Anda"></textarea>
                        </div>
                      </div>
                      <button type="submit" @click="sent" class="btn btn-primary float-right">Submit</button>
                  </form>
              </div>
            </div>
          </div>
      </div>    
    </div>
  </div>
</template>

<script>
import { setTimeout } from 'timers';
export default {
  name: 'app',
  components: {

  },
  data(){
    return{
      nim : '',
      name : '',
      kelas : '',
      jurusan : '',
      skripsi : '',
      tanggal : '',
      jam : '',
      email : '',
      materi : ''
    }
  }, 
  methods:{
    handleRegister(e){
      e.preventDefault()
      e.stopPropagation()
    },
    nimEvent(ev){
      if( ev.key == 'Enter' ){
          if(this.nim !== ''){
            const colnim = document.getElementById('colnim')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Nim Success'))
            colnim.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input NIM'))
            colnim.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    nameEvent(ev){
      if( ev.key == "Enter" ){
          if(this.name !== ''){
            const colname = document.getElementById('colname')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Name Success'))
            colname.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Name'))
            colname.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    kelasEvent(ev){
      if( ev.key == "Enter" ){
          if(this.kelas !== ''){
            const colkelas = document.getElementById('colkelas')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Kelas Success'))
            colkelas.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Kelas'))
            colkelas.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    jurusanEvent(ev){
      if( ev.key == "Enter" ){
          if(this.jurusan !== ''){
            const coljurusan = document.getElementById('coljurusan')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Jurusan Success'))
            coljurusan.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Jurusan'))
            coljurusan.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    skripsiEvent(ev){
      if( ev.key == "Enter" ){
          if(this.skripsi !== ''){
            const colskripsi = document.getElementById('colskripsi')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Skripsi Success'))
            colskripsi.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input skripsi'))
            colskripsi.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    tanggalEvent(ev){
      if( ev.key == "Enter" ){
          if(this.tanggal !== ''){
            const coltanggal = document.getElementById('coltanggal')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Tanggal Success'))
            coltanggal.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Tanggal'))
            coltanggal.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },  
    jamEvent(ev){
      if( ev.key == "Enter" ){
          if(this.jam !== ''){
            const coljam = document.getElementById('coljam')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Jam Success'))
            coljam.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Jam'))
            coljam.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      }, 
    emailEvent(ev){
      if( ev.key == "Enter" ){
          if(this.email !== ''){
            const colemail = document.getElementById('colemail')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Email Success'))
            colemail.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Email'))
            colemail.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
    materiEvent(ev){
      if( ev.key == "Enter" ){
          if( this.materi !== '\n' && this.materi !== '' ){
            const colmateri = document.getElementById('colmateri')
            const div = document.createElement('div')
            div.className = `alert alert-success`
            div.appendChild(document.createTextNode('Input Materi Success'))
            colmateri.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }else{
            const div = document.createElement('div')
            div.className = `alert alert-danger`
            div.appendChild(document.createTextNode('Please Input Materi'))
            colmateri.appendChild(div)
            setTimeout(() => document.querySelector('.alert').remove(),500);
          }
        }
      },
      sent(){
        const input = document.querySelectorAll('.form-control');
          for(var i = 0; i < input.length; i++){
            if(input[i].value == ''){
              console.log('error')
            }
            else if( i == input.length-1 ){
              for(var i = 0; i < 9; i++){
              if(input[i].value !== ''){
              input[i].value = '';}
              }
            }
        }
      }
    }, 
  }

</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

body{
  padding:0;
  margin:0;
}

h1{
  text-shadow: 5px 5px 8px #cccccc;
  color: white;
}
#hero{
    background-image: url(./components/1.jpg);
    background-size: cover;
    background-position: center center;
    position: relative;
    top: 0;
    bottom: 0;
    height: 100vh;
}
#hero-overlay{
    position: absolute;
    background-color: rgba(0, 0, 0, 0.4);
    top: 0;
    bottom: 0;
    height: 100%;
    width: 100%;
}
label{
  color : white;
  font-size: 30px;
}
</style>
