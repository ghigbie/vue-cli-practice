<template>
  <div id="app">
    <Blogs />
    <Navbar />
    <AllFriends :friends="friends"
                @delete="deleteFriend"/>
    <OnlineFriends :friends="friends"/>
  </div>
</template>

<script>
import Navbar from './components/Navbar';
import AllFriends from './components/AllFriends';
import OnlineFriends from './components/OnlineFriends';
import Blogs from './components/Blogs';

export default {
  name: 'app',
  components: {
    Navbar,
    AllFriends,
    OnlineFriends,
    Blogs
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      friends: [
                {name: 'Mario', online: true},
                {name: 'Luigi', online: false},
                {name: 'Toad', online: true},
                {name: 'Bowser', online: false}
      ]
    };
  },
  methods: {
    deleteFriend(payload){
      console.log(payload);
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name;
      });
    }
  }
}
</script>

<style scoped>

</style>
