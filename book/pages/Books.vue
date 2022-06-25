<template>
    <div>
        <h1 v-if="all">{{ all }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'AllBooks',

        async asyncData({ $axios }) {
            try {
                const { data } = await $axios.get('volumes/', {
                    params: { q: 'All'}
                })
                return {
                    all: data
                }
            }
            catch(err){
                console.log(err)
            }
        }

    }
</script>