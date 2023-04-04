<template>
  <div class="container">
      <form v-if="!submited">
          <div class="row" >
              <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                  <!-- Soru 1 -->
                  <!-- Aşağıdaki bilgileri içeren bir Üye Ol sayfası geliştiriniz. -->
                  <!-- Tam Adı (Ad + Soyad) -->
                  <!-- E-mail -->
                  <!-- Şifre -->
                  <!-- Cinsiyet (Kadın/Erkek) -->
                  <!-- <div class="form-group">
                    <label>Ad:</label>
                    <input type="text" class="form-control" v-model="info.name">
                  </div>
                  <div class="form-group">
                    <label>Soyad:</label>
                    <input type="text" class="form-control" v-model="info.surname">
                  </div> -->
                 <appfullName v-model="info.fullname"></appfullName>
                  <div class="form-group">
                    <label>E-mail:</label>
                    <input type="text" class="form-control" v-model="info.mail">
                  </div>
                  <div class="form-group">
                    <label>Şifre:</label>
                    <input type="password" class="form-control" v-model="info.password">
                  </div>
                  <div class="form-group">
                    <label>
                        <input type="radio" v-model="info.gender" value="kadin">Kadın
                    </label>
                    <label>
                        <input type="radio" v-model="info.gender" value="erkek">Erkek
                    </label>
                  </div>
                  <button @click.prevent="submit" class="btn btn-primary">Kayıt ol</button>
                  <!-- Soru 2 -->
                  <!-- Üye Ol formu, Submit EDİLMEDİĞİ SÜRECE ekranda gözükmelidir.-->
                  <!-- Üye Bilgileri Ekranı ise form Submit EDİLDİKTEN SONRA ekranda gözükecektir -->

                  <!-- Soru 3 -->
                  <!-- Yukarıdaki uygulamayı düzenleyerek Tam Ad (Ad + Soyad) alanı için bir Form Kontrol Elemanı üretiniz -->
              </div>
          </div>
      </form>
      <div class="row" v-else>
          <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
              <div class="panel panel-info">
                  <div class="panel-heading">
                      <h4>Girdiğiniz Bilgier</h4>
                  </div>
                  <div class="panel-body">
                      <p>Tam Ad:   {{info.fullname}}</p>
                      <p>E-mail:   {{info.mail}}</p>
                      <p>Şifre:    {{info.password}}</p>
                      <p>Cinsiyet: {{info.gender}}</p>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import Fullname from "./fullName.vue";
  export default {
    data(){
        return{
            info:{
            fullname:"Süm Kar",
            mail:"",
            password:"",
            gender:""
            },
            submited:false
        }
    },
    methods:{
        submit(){
            this.submited=true;
        }
    },
    components:{
      appfullName:Fullname
    }
  }
</script>

<style>
</style>
