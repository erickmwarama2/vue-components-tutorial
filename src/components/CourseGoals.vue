<template>
    <ul>
        <li v-for="goal in goals" :key="goal">
            <slot anotherProp="Erick" :item="goal"></slot>
        </li>
    </ul>
</template>
<script>
export default {
    data() {
        return {
            goals: ['Finish the course', 'Learn vue']
        }
    }
}
</script>