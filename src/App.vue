<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

                <button class="btn btn-primary" v-my-on:click="toogleParagraph">Click me</button>
                <p v-if="show">Now you can see me</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                show: false
            };
        },
        directives: {
            'my-on': function(el, binding, vnode) {
                var event = binding.arg;
                var func = binding.value;
                el.addEventListener(event, func);
            }
        },
        methods: {
            toogleParagraph() {
                this.show = !this.show;
            }
        }
    }
</script>

<style>
</style>
