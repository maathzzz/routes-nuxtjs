<script setup lang="ts">

  enum Gender {
    GIRL = "Girl",
    BOY = "Boy",
    UNISEX = "Unisex"
  }

  enum Popularity {
    TRENDY = "Trendy",
    UNIQUE = "Unique",
  }

  enum Length {
    SHORT = "Short",
    LONG = "Long",
    ALL = "All"
  }

  interface OptionsState {
    gender: string;
    popularity: string;
    length: string;
  }

  const obj: OptionsState = {
    gender: Gender.GIRL,
    popularity: Popularity.TRENDY,
    length: Length.SHORT,
  }

  const options = reactive<OptionsState>({
    gender: Gender.GIRL,
    popularity: Popularity.TRENDY,
    length: Length.SHORT,
  })

</script>

<template>
  <div class="container  ">
    <h1> Name Generator </h1>
    <p> Choose your options and click the "Find Names" button below.</p>
    <div class="options-container">
      <div class="option-container">
          <h4> 1) Choose a gender </h4>
          <div class="option-buttons">
            <button class="option option-left" :class="options.gender === Gender.BOY && 'option-active'"> Boy </button>
            <button class="option" :class="options.gender === Gender.UNISEX && 'option-active'"> Unisex </button>
            <button class="option option-right" :class="options.gender === Gender.GIRL && 'option-active'"> Girl </button>
          </div>
          <div class="option-container">
              <h4> 2) Choose a the name's popularity </h4>
              <div class="option-buttons">
                <button class="option option-left" :class="options.popularity === Popularity.TRENDY && 'option-active'"> Trendy </button>
                <button class="option option-right" :class="options.popularity === Popularity.UNIQUE && 'option-active'"> Unique </button>
              </div>
          </div>
          <div class="option-container">
            <h4> 3) Choose name's length </h4>
              <div class="option-buttons">
                <button class="option option-left" :class="options.length === Length.LONG && 'option-active'"> Long </button>
                <button class="option" :class="options.length === Length.SHORT && 'option-active'"> Short </button>
                <button class="option option-right" :class="options.length === Length.ALL && 'option-active'"> All </button>
              </div>
          </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .container{
    font-family: Arial, Helvetica, sans-serif;
    color: rgb(27, 60, 138);
    max-width: 50rem;
    margin: 0 auto;
    text-align: center; 
  }

  h1 {
    font-size: 3rem;
  }

  .options-container{
    background-color: rgb(255, 238, 236);
    border-radius: 2rem;
    padding: 1rem;
    width: 95%;
    margin: 0 auto;
    margin-top: 2rem;
    position: relative;
  }

  .option-container{
    margin-bottom: 2rem;
  }

  .option {
    background: white;
    outline: 0.15rem solid rgb(249, 87, 89);
    border: none;
    padding: 0.75rem;
    width: 12rem;
    font-size: 1rem;
    color: rgb(27,60,138);
    cursor: pointer;
    font-weight: 200;
  }

  .option-active {
    background-color: rgb(249, 87, 89);
    color: white;
  }

  .option-left {
    border-radius: 1rem 0 0 1rem;
  }

  .option-right {
    border-radius: 0 1rem 1rem 0;
  }
</style>