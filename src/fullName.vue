<template>
    <div>
         <div class="form-group">
            <label>Ad:</label>
            <input type="text" class="form-control" :value="name" @input="nameChange(true,$event)">
          </div>
          <div class="form-group">
            <label>Soyad:</label>
            <input type="text" class="form-control" :value="surname" @input="nameChange(false,$event)">
          </div>
     </div>
</template>
<script>
export default{
  props:["value"],
  computed:{
    name(){
      return this.value.split(" ")[0]
    },
    surname(){
      return this.value.split(" ")[1]
    }
  },
  methods:{
    nameChange(isfirst,event){
      let fullName="";
      if(isfirst){
        fullName=event.target.value+" "+this.surname;
      }else{
        fullName=this.name+" "+event.target.value
      }
      this.value=fullName;
      this.$emit("input",this.value)
    }
  }
}
</script>