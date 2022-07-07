<template>
  <header>
    <div class="menu-esquerdo">
      <span> <RouterLink to="/">Home</RouterLink> </span>
      <span></span>
      <span> <RouterLink to="/times">Times</RouterLink> </span>
      <span></span>
      <span> <RouterLink to="/jogadores">Jogadores</RouterLink> </span>
    </div>
  </header>
</template>

<style>
header span {
  padding: 0 20px;
}

header {
  height: 10%;
  background-color: #004DA8;
  color: #ffffff;
  font-size: 1.5rem;
  display: flex;
  align-items: center;
  border-radius: 10px;
  padding-left: 50px;
  justify-content: space-between;
}

</style>
