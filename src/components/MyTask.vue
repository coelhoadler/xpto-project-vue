<template>
    <MyBox>
        <div class="columns">
            <div class="column is-7">{{ taskObj?.description || 'Tarefa sem descrição' }}</div> 
            <div class="column is-5">
                <StopWatch :timeInSeconds="taskObj?.timeInSeconds" />
            </div>
        </div>
    </MyBox>
</template>

<script>
import { defineComponent } from 'vue';
import StopWatch from './StopWatch.vue';
import MyBox from './MyBox.vue';

    export default defineComponent({
        name: 'MyTask',
        components: {
            StopWatch,
            MyBox
        },
        props: {
            taskObj: {
                type: Object,
                required: true
            }
        }
    })
</script>

<style scoped></style>