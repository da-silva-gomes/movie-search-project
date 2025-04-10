<template>
  <div class="navbar-wrapper">
    <div class="navbar-content">
      <h3 class="logo">
        <slot name="heading"></slot>
      </h3>
      <div>
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<style scoped />
