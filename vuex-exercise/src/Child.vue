<template>
    <div>
        Child counter : {{childCounter}}
        <!-- <hr>
        Child counter : {{this.$store.state.counter}} <br>
        <button>+</button>
        <button>-</button> -->
    </div>
</template>

<script>
export default {
    computed: {
        childCounter(){
            return this.$store.getters.getCounter;
        }
    },
}
</script>