<template>
    <span>
        {{dd}}.{{mm}}.{{yyyy}}
    </span>
</template>

<script>
export default {
    name: 'HireDisplay',
    computed: {
        dd(){
            var dd = new Date(this.hireDate).getDate()
            if (dd < 10) dd = '0' + dd
            return dd
        },
        mm(){
            var mm = new Date(this.hireDate).getMonth() + 1
            if (mm < 10) mm = '0' + mm
            return mm
        },
        yyyy(){
            var yyyy = new Date(this.hireDate).getFullYear()
            return yyyy
        },
    },
    props: ['hireDate'] 
}
</script>
