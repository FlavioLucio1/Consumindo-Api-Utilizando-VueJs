<template>
  <div>

    <div
    v-for="user,index in users"
    :key="index"
    >

      <User 
        :user="user"
      />

    </div>
    
  </div>
</template>

<script>
function GetAPI(url)
{
    let request = new XMLHttpRequest()
    request.open("GET",url,false);
    request.send()
    return request.responseText
}

function main()
{
    let data = GetAPI("https://5ff75c21e7164b0017e1a82d.mockapi.io/api/v1/empreendimentos")
    let usersData = JSON.parse(data)
    return usersData
}

//main();

import User from '../components/Users/User.vue'

  export default {
    name: 'Home',

    components: {
      User
    },
    data(){
      return{
        users: main()
      }
    }
  }

</script>
