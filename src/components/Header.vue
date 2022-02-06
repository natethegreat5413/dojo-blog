<template>
    <div class="wrapper">
        <div class="links">
            <h2 class="link">Vue Playground</h2>
            <router-link to="/" class="link">Blog</router-link>
            <router-link to="/" class="link">Pricing</router-link>
            <router-link to="/" class="link">Company</router-link>
            <router-link to="/" class="link">Jobs</router-link>
        </div>
        <div class="login">
            <router-link to="/" class="link">Login</router-link>
            <button @click="signUp" class="signup">Sign up</button>
        </div>
    </div>
</template>

<script>
import { useRouter } from "vue-router";

export default {
    setup() {
        const router = useRouter();
        const signUp = () => {
            router.push("Signup");
        };

        return {
            signUp,
        };
    },
};
</script>

<style>
.wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.links {
    display: flex;
    flex-direction: row;
    align-items: baseline;
    text-decoration: none;
}
.link {
    padding: 15px;
    color: unset;
}
.login {
    display: flex;
    flex-direction: row;
    align-items: baseline;
}
.signup {
    padding: 8px;
    border-radius: 30px;
    width: 80px;
    background-color: #fff;
    border-color: silver;
    border-width: 1.5px;
}
</style>
