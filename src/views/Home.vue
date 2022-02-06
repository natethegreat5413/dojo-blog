<template>
    <div class="home">
        <Header />
        <h1>Vue Playground</h1>
        <div v-if="error">{{ error }}</div>
        <PostList :posts="posts" />
    </div>
</template>

<script>
import getPosts from "../composables/getPosts";
import PostList from "../components/PostList.vue";
import Header from "../components/Header.vue";

export default {
    name: "Home",
    components: { PostList, Header },
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

<style scoped>
.home {
    padding: 12px;
}
</style>
