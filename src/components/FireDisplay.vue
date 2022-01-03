<template>
    <span v-if="fireDate"> {{dd}}.{{mm}}.{{yyyy}}</span>
    <span v-else> 
        

    </span>
</template>

<script>
export default {
    name: 'FireDisplay',
    computed: {
        dd(){
            var dd = new Date(this.fireDate).getDate()
            if (dd < 10) dd = '0' + dd
            return dd
        },
        mm(){
            var mm = new Date(this.fireDate).getMonth() + 1
            if (mm < 10) mm = '0' + mm
            return mm
        },
        yyyy(){
            var yyyy = new Date(this.fireDate).getFullYear()
            return yyyy
        },
    },
    props: ['fireDate'] 
}
</script>
