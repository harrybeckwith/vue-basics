<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <server 
            v-for="server in servers" 
            :key="server.id"
            :id="server.id"
            :status="server.status"
            :server="server"
            > </server>
        </ul>
    </div>
</template>

<script>
import Server from './Server.vue';
export default {
    data() {
        return {
            servers: [
                {id: 1, status: 'Normal'},
                {id: 2, status: 'Critical'},
                {id: 3, status: 'Unknown'},
                {id: 4, status: 'Danger'},
            ]
        }
    },
    methods: {
        getStatus(status) {
            console.log(status);
        }
    },
    components: {
        Server
    }
}
</script>
    
<style>

</style>
