<template>
    <Box>
        <div class="columns">
            <div class="column is-7">
                {{ task.description || 'Tarefa não definida' }}
            </div>
            <div class="column">
                <Stopwatch
                    :time="task.time"
                />
            </div>
        </div>
    </Box>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Stopwatch from './Stopwatch.vue';
import Tasks from '../interfaces/Tasks';
import Box from './Box.vue';

export default defineComponent({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Task',

    components: {
        Stopwatch,
        Box
    },
    props: {
        task: {
            type: Object as PropType<Tasks>,
            required: true
        }
    }
});
</script>
