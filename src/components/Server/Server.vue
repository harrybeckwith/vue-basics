<template>
    <li class="list-group-item" @click="getStatus">
        Server #{{ id }}
    </li>
</template>
<script>
import { eventBus } from '../../main';
export default {
    props: ['id', 'status', 'server'],

    methods: {
        getStatus() {
            eventBus.$emit('serverStatus', this.server);
        }
    }
}
</script>
