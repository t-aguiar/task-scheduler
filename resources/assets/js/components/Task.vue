<template>
    <div class="row" >
        <div class="col-lg-1 col-md-1 col-sm-1">
            <input type="checkbox" :id=task.name v-model="task.isComplete">
        </div>
        <div class="col-lg-8 col-md-8 col-sm-8">
            <label :for=task.name>{{ task.name }}</label>
        </div>
        <div class="col-lg-3 col-md-3 col-sm-3"
             v-bind:class="task.isComplete ? 'text-success' : 'text-danger'">
            {{ task.completedAt }}
        </div>
    </div>
</template>

<script>
    export default {
        name: 'task',
        props: [
            'task',
        ],
        data: function () {
            return {}
        },
        watch: {
            'task.isComplete': function () {
                var ts = 'Incomplete';

                if (this.task.isComplete) {
                    ts = this.$moment().format('LLL');
                }

                this.task.completedAt = ts;
            },
        }
    }
</script>

<style scoped>

</style>