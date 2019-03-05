<template>
  <div id="app">
    <div id="hero">
        <div id="hero-overlay">
          <div class="container">
            <div class="row mainrow">
              <div class="col-sm-8 offset-sm-2 mt-3">
                <h1 class="text-center">
                  <span>F</span>
                  <span>O</span>
                  <span>R</span>
                  <span>M</span> &nbsp;
                  <span>M</span> 
                  <span>A</span>
                  <span>H</span>
                  <span>A</span>
                  <span>S</span>
                  <span>I</span>
                  <span>S</span>
                  <span>W</span>
                  <span>A</span>
                </h1>
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
              input[i].style.borderColor = "red"
            }
            else if( i == input.length-1 ){
              for(var i = 0; i < 9; i++){
              if(input[i].value !== ''){
              input[i].value = '';
              input[i].style.borderColor = "white"
              }
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
  color: white;
  text-align: center;
}
h1 span{
  animation: animate 12.5s linear infinite;
}
hi span:nth-child(1){
  animation-delay: 0s;
}
hi span:nth-child(2){
  animation-delay: 1s;
}
hi span:nth-child(3){
  animation-delay: 2s;
}
hi span:nth-child(4){
  animation-delay: 3s;
}
hi span:nth-child(5){
  animation-delay: 4s;
}
hi span:nth-child(6){
  animation-delay: 5s;
}
hi span:nth-child(7){
  animation-delay: 6s;
}
hi span:nth-child(8){
  animation-delay: 7s;
}
hi span:nth-child(9){
  animation-delay: 8s;
}
hi span:nth-child(10){
  animation-delay: 9s;
}
hi span:nth-child(11){
  animation-delay: 10s;
}
hi span:nth-child(12){
  animation-delay: 11s;
}
hi span:nth-child(13){
  animation-delay: 12s;
}
@keyframes animate
{
  0%,100%
  {
    color:#fff;
    filter:blur(2px);
    text-shadow: 0 0 10px #690718,
                0 0 20px #690718,
                0 0 40px #690718,
                0 0 80px #690718,
                0 0 120px #690718,
                0 0 200px #690718,
                0 0 300px #690718,
                0 0 400px #690718;
  }
  5%,95%
  {
    color:white;
    filter:blur(0px);
    text-shadow: none;
  }

}
.form-group{
  opacity: 0.8;
}
.form-group:hover{
  opacity: 1;
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

@media only screen and (max-width: 700px) {
  #hero{
    background-image: url(./components/1.jpg);
    background-size: cover;
    background-position: center center;
    position: relative;
    top: 0;
    bottom: 0;
    height: 125vh;
  }
}
@media only screen and (max-width: 450px) {
  #hero{
    background-image: url(./components/1.jpg);
    background-size: cover;
    background-position: center center;
    position: relative;
    top: 0;
    bottom: 0;
    height: 160vh;
  }
}
@media only screen and (max-width: 350px) {
  #hero{
    background-image: url(./components/1.jpg);
    background-size: cover;
    background-position: center center;
    position: relative;
    top: 0;
    bottom: 0;
    height: 190vh;
  }
}

</style>
