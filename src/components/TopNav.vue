<template>
  <div class="Nav-Container">
    <div class="Elements-Container">
      <div class="Nav-Element">
        <span>القرأن للأميين</span>
        <img src="../assets/2omyen.png" alt="القرأن للأميين" />
      </div>

      <div class="Nav-Element">
        <span>القرأن للمكفوفين</span>
        <img src="../assets/blind.png" alt="القرأن للمكفوفين" />
      </div>

      <div class="Nav-Element">
        <span>القرأن الكريم</span>
        <img src="../assets/moshaf.png" alt="القرأن الكريم" />
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
.Nav-Container {
  z-index: 10;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  align-content: center;
  text-align: center;
  width: 100%;
  height: 75px;
  background-color: #fff;
  box-shadow: 0px 0px 156.2px 3px rgba(0, 0, 0, 0.25);
}
.Elements-Container {
  margin: auto;
  display: inline-flex;
  align-items: center;
  gap: 250px;
}
.Nav-Element {
  display: flex;
  align-content: center;
  justify-content: center;
  /* width: 151px; */
  height: 50px;
}
.Nav-Element img {
  width: 50px;
  height: 50px;
}
.Nav-Element span {
  text-overflow: none;
  color: #000;
  font-family: "Simplified Arabic";
  font-size: 24px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
@media (max-width: 960px) {
  .Nav-Container {
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .Elements-Container {
    gap: 60px;
    display: flex;

    flex-direction: row;
    align-items: center;
    justify-content: center;
    margin: 0;
  }
  .Nav-Element {
    height: fit-content;
  }
  .Nav-Element span {
    font-size: 20px;
  }

  .Nav-Element img {
    width: 40px;
    height: 40px;
  }
}

@media (max-width: 480px) {
  .Nav-Container {
    height: auto;
  }
  .Elements-Container {
    flex-direction: column;
    gap: 10px;
  }

  .Nav-Element {
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .Nav-Element span {
    font-size: 18px;
  }

  .Nav-Element img {
    width: 30px;
    height: 30px;
  }
}
</style>
