<template>
    <div>
        <p>Home</p>
        <task
            v-for="item in tasks"
            v-bind:task="item"
        ></task>
    </div>
</template>

<script>
    import Task from "../components/Task";

    export default {
        components: {Task},
        name: "home",
        data: function () {
            return {
                tasks: [
                    {name: 'Do work', isComplete: true, completedAt: this.$moment("2018-03-30").format('lll') },
                    {name: 'Fer Rlz', isComplete: false, completedAt: 'Incomplete'},
                    {name: 'Srsly!!', isComplete: false, completedAt: 'Incomplete'},
                ]
            };
        },
    }
</script>

<style scoped>
    p {color: #005cbf}
</style>