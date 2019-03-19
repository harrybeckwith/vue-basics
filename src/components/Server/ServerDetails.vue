<template>
    <div class="col-xs-12 col-sm-6">
    
        <p v-if="!serverDetails">Select a server</p>
        <p v-else>Server #{{ serverDetails.id }} {{ serverDetails.status }}</p>
        <button v-if="serverDetails" @click="changeStatus">Change to Normal</button>
    </div>

</template>

<script>
import { eventBus } from '../../main';

export default {
    data() {
        return {
            serverDetails: null
        }
    },
    created() {
        eventBus.$on('serverStatus', (server)=> {
            this.serverDetails = server
        })
    }, 
    methods: {
        changeStatus() {

            this.serverDetails.status = 'Normal';
        }
    }
}
</script>
    
<style>

</style>
