<template>
    <section
        class="View-section overflow-hidden d-flex flex-column justify-content-center align-items-center"
    >
        <div class="logo">
            <img src="../assets/Images/logo.png" alt="logo" class="logo-img" />
            <h1 class="logo-title">Nice Admin</h1>
        </div>
        <div class="card">
            <div class="card-body">
                <div class="text-center">
                    <h2 class="card-title">Create An Account</h2>
                    <p class="card-subtitle">
                        Enter your personal details to create account
                    </p>
                </div>
                <form class="mt-3">
                    <div class="mb-3">
                        <label class="form-label">Your Name</label>
                        <input
                            v-model="fName"
                            type="text"
                            class="form-control"
                            required
                        />
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Your Email</label>
                        <input
                            v-model="email"
                            type="email"
                            class="form-control"
                            required
                        />
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Username</label>
                        <div class="input-group">
                            <span class="input-group-text">@</span>
                            <input
                                v-model="username"
                                type="text"
                                class="form-control"
                                required
                            />
                        </div>
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Password</label>
                        <input
                            v-model="password"
                            type="password"
                            class="form-control"
                            required
                        />
                    </div>
                    <div class="form-check mb-3">
                        <input
                            id="checkbox-input"
                            type="checkbox"
                            class="form-check-input"
                            required
                            v-model="checking"
                        />
                        <label for="checkbox-input" class="form-check-label"
                            >I agree and accept the
                            <span class="text-primary"
                                >terms and conditions</span
                            ></label
                        >
                    </div>
                    <button
                        @click="submitButton"
                        type="submit"
                        class="btn btn-primary m-0 w-100"
                    >
                        Create Account
                    </button>
                    <div class="mb-3">
                        <p class="login-text">
                            Already Have An Account?
                            <router-link to="./login">Login</router-link>
                        </p>
                    </div>
                </form>
            </div>
        </div>
        <footer class="border-0">
            <p class="fs-6">
                Designed by <span class="text-primary">BootstrapMade</span>
            </p>
        </footer>
    </section>
</template>

<script>
export default {
    name: "RegisterView",
    data: () => {
        return {
            fName: "",
            email: "",
            username: "",
            password: "",
            checking: "",
        };
    },
    methods: {
        submitButton() {
            if (
                !this.fName ||
                !this.email ||
                !this.username ||
                !this.password ||
                !this.checking
            )
                return;
            this.$router.push("/home/dashboard");
        },
    },
};
</script>

<style scoped>
section {
    height: 100vh;
    margin-top: -100px;
}
.logo {
    display: flex;
    align-items: center;
}
.logo-title {
    font-size: 28px;
    color: #012970;
}
.logo-img {
    width: 25px;
    height: 25px;
    margin-right: 5px;
}
.card-subtitle {
    font-size: 14px;
}
.login-text {
    margin-top: 8px;
    font-size: 14px;
}
</style>
