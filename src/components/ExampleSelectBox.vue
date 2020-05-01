<template>
    <div>
        <select v-model="myvalue" @change="changed(myvalue)">
            <option v-for="source in bookingSource" :key="source.id" :value="source.id">{{source.name}}</option>
        </select>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            bookingSource: null,
            myvalue: null,
        };
    },
    created: function() {
        console.log('in created');
    },
    mounted: function() {
        axios.get("http://www.json-generator.com/api/json/get/cpEmGeQTuG?indent=2")
            .then((result) => {
                console.log('i got result', result);
                this.bookingSource = result['data'];
            })

        console.log('in mounted');
    },
    methods: {
        changed(e) {
            // console.log('i was changed', e);
            this.$emit('custom-change', e);
        }
    }

};
</script>

<style scoped>
</style>