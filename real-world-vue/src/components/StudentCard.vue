<template>
    <div class="event-class">
        <div class="event-card">
            <h4>{{ student.name + " "}}  {{ " " + student.surname }}</h4>
            <h4>{{ student.gpa }}</h4>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { type EventItem } from '@/type';
import { PropType } from 'vue'
const props = defineProps({
    student: {
        type: Object as PropType<EventItem>,
            require: true
    }
})

</script>

<style scoped>
.event-card {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
}

.event-card:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>