<template>
  <h1 class="text-center">About me</h1>
  <div class="container d-flex justify-content-center">
  <div class="card mb-3" style="max-width: 100%;">
<div class="row g-0">
  <div class="col-md-4">
    <img :src="picture" class="img-fluid rounded-start" alt="..." :width="size">
  </div>
  <div class="col-md-8">
    <div class="card-body d-flex">
      <div class="container w-100">
      <h5 class="card-title">{{ getfullname() }}</h5>
  <form @submit.prevent="submitform">
      <div class="input-group flex-nowrap w-100">
<span class="input-group-text" id="addon-wrapping"><i class="bi bi-person-circle"></i></span>
<input type="text" class="form-control shadow-none" @input="setNickname" placeholder="Nickname" aria-label="Username" aria-describedby="addon-wrapping">
<button type="submit" class="btn btn-success">Save</button>
</div>  

</form>
     

<p class="card-text my-0"> Nickname : {{ nickname }}</p>
      <p class="card-text my-0">Age: {{ age }}</p>
      <p class="card-text my-0">Address : {{ address }}</p>
          <div class="container" >
          <p v-if="hobby.length ===0">ไม่มีงานอดิเรก</p>
          <div v-else>
          
      <p class="card-text my-0">Hobbys : </p>

          <ul style="color: aliceblue;">
              <li v-for="itme in hobby">{{ item }}</li>
          </ul>
      </div>
      </div>
      <div class="container">
          <p class="card-text my-0">Generals : </p>
          <ul>
          <li style="color: aliceblue;" v-for="(value,key) in general" :key="key">{{ key }} : {{ value }}</li>
          </ul>
      </div>
          <button type="button" class="btn btn-primary mx-2" @click="showdata()">Click to see</button>
          <button type="button" class="btn btn-success mx-2" @click="plus(1)">Increment</button>
          <button type="button" class="btn btn-danger mx-2" @click="del(1)">Decrement</button>
      </div>


    <div class="container">

    </div>
  </div>
  </div>
  
</div>
</div>
</div>
</template>

<script>
  export default{
      data(){
          return{
              firstName : 'kamin',
              lastName : 'P',
              age : 8,
              address : 'Chonburi',
              picture : 'https://i.pinimg.com/1200x/e8/38/93/e838936ed4cb8a624f59e7ac132741eb.jpg',
              size : 1000,
              hobby: [],
              general: {gender:'Male',weight:120,height: 178,status : false},
           git config --global user.name "FIRST_NAME LAST_NAME"

   nickname : ''
          }
      },
      methods: {
          getfullname(){
              return `${this.firstName} ${this.lastName} `
          },
          showdata(){
              alert(this.firstName)
          },
          plus(value){
              this.age += value
          },
          del(value){
              this.age -= value
          },
          setNickname(event){
              this.nickname=event.target.value
          },
          submitform(){
              alert("Save success")
          }
      }
  }
</script>
