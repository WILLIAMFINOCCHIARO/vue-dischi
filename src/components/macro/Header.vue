<template>
<header>
  <div class="container-fluid d-flex align-items-center">
    <div class="row  ">
      <div class="col-3 ">
        <img src="../../assets/img/png-clipart-spotify-logo-spotify-computer-icons-podcast-music-apps-miscellaneous-angle.png" alt="">
      </div>
    </div>
  </div>
</header>
  
</template>


<script>
export default {
  name:"Header",
}
</script>

<style lang="scss" scoped>
.container-fluid{
  height:100px;
  background-color: #2e3a46;
  img {
    height:50px;
    filter:invert(1);
    border-radius:100px;
  }
}

</style>
