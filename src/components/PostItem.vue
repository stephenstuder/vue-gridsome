<template>
    <div class="post-item">
        <span class="date">{{ date }}</span>
        <g-link :to="post.path" class="read">{{ post.title }}</g-link>
        <span class="time-to-read">
            <i>{{ post.timeToRead }} min read</i>
        </span>
    </div>
</template>

<script lang="ts">
export default {
    props: ["post"],
    computed: {
        date() {
            return this.post.date.substring(0, this.post.date.length - 4);
        }
    }
};
</script>
