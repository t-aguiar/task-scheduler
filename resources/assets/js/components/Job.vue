<template>
    <div>
        <p>Job Name Here</p>
        <div>
            <p>Task List</p>
            <task v-for="item in tasks"
                  v-bind:task="item">
            </task>
        </div>
    </div>
</template>

<script>
    import Task from '../components/Task';

    export default {
        name: "job",
        components: {Task},
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

</style>