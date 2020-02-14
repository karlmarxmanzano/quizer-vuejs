<template>
    <div class="col-md-8 ">
        <div class="card text-white bg-success mb-3">
            <div class="card-body">
                <h1 class="card-title">Correct!</h1>
                <button class="btn btn-outline-light" @click="onNextQuestion">Next Question</button>
            </div>
        </div>
    </div>
</template>
<style>

</style>
<script>
    export default{
        methods: {
            onNextQuestion() {
                this.$emit('confirmed');
            }
        }
    }
</script>
