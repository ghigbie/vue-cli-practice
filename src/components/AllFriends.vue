<template>
    <div id="all-friends">
        <h2>All Friends</h2>
        <div v-for="friend in friends">
            <span> {{ friend.name }} </span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AllFriends',
    data(){
        return {
            friends: [
                {name: 'Mario', online: true},
                {name: 'Luigi', online: false},
                {name: 'Toad', online: true},
                {name: 'Bowser', online: false}
            ]
        }
    }
}
</script>

<style scoped>

</style>
