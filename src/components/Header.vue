<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand">Shopping List</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav me-auto">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page">
                <router-link to="/">Home</router-link>
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link">
                <router-link to="/App">App</router-link>
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link">
                <router-link to="/about">About</router-link>
              </a>
            </li>
          </ul>
          <div class="d-flex">
            <button class="btn btn-outline-success" @click="login">
              {{ logStatus }}
            </button>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import { computed } from 'vue';
import { useStore } from 'vuex'

export default {
  name: "Header",
  setup() {
    const store = useStore()

    const logStatus = computed(() => store.state.logStatus)

    const login = () => store.commit('login')

    return { logStatus, login }
  },
};
</script>

<style scoped>
.bg-light {
  background-color: #52c7b17a !important;
}
a {
  text-decoration: none;
  color: #338f7ede;
}
nav .router-link-active {
  color: #000;
  font-weight: 700;
}

@media (max-width: 992px) {
  ul .me-auto {
    margin-right: 0;
  }
}
</style>