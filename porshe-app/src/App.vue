<script setup>
</script>

<template>
  <main>
    <router-view v-slot="{Component}">
      <Transition name="fade" mode="out-in" >
        <component :is="Component" :key="$route.path"></component>
      </Transition>
    </router-view>
  </main>
</template>

<style lang="scss">
$primary: #d84c4d;
main {
  display: flex;
  align-items: center;
  min-height: 100vh;
  position: relative;

  &::before {
    content: "";
    position: absolute;
    top: -689px;
    bottom: 0;
    right: -203px;
    width: 70%;
    height: 200vh;
    // background:$primary; // rebeccapurple; //$primary; //
    z-index: -1;
    transform: rotate(-40deg);
  }
}
  button {
    color: #fff;
  }

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 1s;
  }

  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }
</style>
