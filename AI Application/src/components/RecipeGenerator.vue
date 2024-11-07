<template>
  <div class="container">
    <h1>AutoChef</h1>
    
    <div class="input-section">
      <input type="text" v-model="ingredients" placeholder="Enter ingredients here..." />
    </div>

    <div class="checkboxes">
      <div class="checkbox-item" v-for="(option, index) in options" :key="index">
        <input type="checkbox" v-model="option.checked" :id="'option' + index">
        <label :for="'option' + index">{{ option.label }}</label>
      </div>
    </div>

    <button id="submit-btn" @click="generateRecipes">Submit</button>

    <div class="recipes">
      <div class="recipe-box" v-for="(recipe, index) in recipes" :key="index">
        {{ recipe }}
      </div>
    </div>

    <div class="photo-icons">
      <div class="photo-icon" v-for="(icon, index) in photoIcons" :key="index"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AutoChef',
  data() {
    return {
      ingredients: '',
      options: [
        { label: 'Option 1', checked: false },
        { label: 'Option 2', checked: false },
        { label: 'Option 3', checked: false }
      ],
      recipes: [],
      photoIcons: [1, 2, 3]  // Placeholder for photo icon elements
    };
  },
  methods: {
    generateRecipes() {
      // Placeholder recipes for demonstration; replace with API call
      this.recipes = ["Recipe A", "Recipe B", "Recipe C", "Recipe D", "Recipe E"];
    }
  }
};
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f4f4f4;
}

.container {
  text-align: center;
  max-width: 600px;
  padding: 20px;
  background-color: #fff;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

h1 {
  font-size: 2em;
  margin-bottom: 10px;
}

.input-section {
  margin-bottom: 20px;
}

input[type="text"] {
  width: 80%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.checkboxes {
  display: flex;
  justify-content: space-around;
  margin: 15px 0;
}

.checkbox-item {
  display: flex;
  align-items: center;
}

.checkbox-item input {
  margin-right: 5px;
}

#submit-btn {
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

#submit-btn:hover {
  background-color: #45a049;
}

.recipes {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
}

.recipe-box {
  width: 18%;
  padding: 10px;
  background-color: #e8e8e8;
  border: 1px solid #ddd;
  border-radius: 4px;
  text-align: center;
  height: 100px;
}

.photo-icons {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
}

.photo-icon {
  width: 40px;
  height: 40px;
  background-color: #ddd;
  border-radius: 50%;
}
</style>
