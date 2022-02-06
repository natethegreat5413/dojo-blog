<template>
    <h1>Blog Home</h1>
    <div v-if="error">{{ error }}</div>
    <PostList :posts="posts" />
</template>

<script>
import getPosts from "../composables/getPosts";
import PostList from "../components/PostList.vue";

export default {
    name: "Blog-Home",
    components: { PostList },
    setup() {
        const { posts, error, load } = getPosts();

        load();

        return {
            posts,
            error,
        };
    },
};
</script>

<style></style>
