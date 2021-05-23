<template>
    <div class="post-list">
        <h1>{{ year }}</h1>
        <PostItem :key="post.node.id" v-for="post in this.postsByYear" :post="post.node" />
    </div>
</template>

<script lang="ts">
import PostItem from "./PostItem.vue";

export default {
    props: ["year"],
    components: {
        PostItem
    },
    computed: {
        postsByYear() {
            const posts = this.$page.allPost.edges;
            return posts.filter((post) => {
                return post.node.date.includes(this.year);
            });
        }
    }
};
</script>
