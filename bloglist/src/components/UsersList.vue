<template>
    <!-- <p>Testing fetching</p> -->
    <div class="info1">
        <div class="card" v-for="dt in response" :key="dt.id">
            <div class="img">
                <img :src="dt.avatar" alt="Images">
            </div>
            <div class="info">
                <p>{{ dt.email }}</p>
                <p>{{ dt.first_name }}  {{ dt.last_name }}</p>
                <!-- <p></p> -->
            </div>

        </div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            response: [],
        }
    },
    created() {
        this.getUsersList()
    },
    methods: {
        async getUsersList() {
            // const res =
            return axios.get('https://reqres.in/api/users/').then(dt => {
                this.response = dt.data.data
                console.log(this.response)
            })
            // const data = await res.json()
            // console.log(data.data)
        }
    }
}
</script>
<style>
.card{
    display: flex;
    flex-direction: row;
    margin: 50px;
}
.info{
    margin-left: 50px;
}
</style>