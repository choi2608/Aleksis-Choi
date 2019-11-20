<template>
  <div>
      <h1>Users</h1>
      <ul>
        <li v-for="(user, i) in users" :key="user.id" @click="changeName(user.name)" @dblclick="removeUser(i)">
          {{user.id}} {{ user.name}} 
          <input type="text" :value="user.name" :id="user.id" v-show="flag">
        </li>
        
      </ul>
      <hr>
      <div>
        <input type="text" v-model="index">
        <button @click="searchUser">Search user test</button>
      </div>
  </div>
</template>

<script>
export default {
    data()  {
        return {
          flag: false,
          users: [
            {
                name: 'Vasya',
                id: 1
            },
            {
                name: 'Petya',
                id: 2
            },
            {
                name: 'Lena',
                id: 3
            },
            {
                name: 'Katya',
                id: 4
            },
            {
                name: 'Vanya',
                id: 5
            },
            {
                name: 'Tolik',
                id: 6
            },
          ],
          index: ''
        }
    },
    methods: {
      alertName(e) {
          alert(
            e
          )
      },
      searchUser() {
        let username = '';
          if (this.index){
            for (var i = 0; i< this.users.length; i++) {
              if (this.users[i].id <= this.index)
               username += this.users[i].name+' '
             } 
          }
          console.log(username)
      },
      removeUser(e){
        this.users.splice(e, 1)
      },
      changeName(e){
        this.flag = !this.flag
      }
    },

    computed:{
      
    }
}
</script>

<style>
  ul,li {
    display: block;
    text-align: left;
  }
</style>