<template>
    <div class="container">
        <div class="header"> <!-- Added header section -->
            <h1>AutoChef</h1>
            <img src="../assets/logo.png" alt="Logo" class="logo" />
        </div>
      
        <div class="sample-text">
            <p>Welcome to AutoChef! Enter your ingredients below and let us suggest some recipes for you!</p>
        </div>

      <div class="input-section">
        <div class="input-container">
                <input type="text" placeholder="Enter ingredients here..." />
                <button id="submit-btn" @click="generateRecipes">Submit</button>
        </div>
        <div class="checkboxes">
        <div class="checkbox-item" v-for="(option, index) in options" :key="index">
          <input type="checkbox" v-model="option.checked" :id="'option' + index">
          <label :for="'option' + index">{{ option.label }}</label>
        </div>
      </div>
      </div>
  
      <div class="recipes">
        <div class="recipe-box" v-for="(recipe, index) in recipes" :key="index">
          {{ recipe }}
        </div>
      </div>
  
      <div class="photo-icons">
        <div class="photo-icon">
            <img src="../assets/darshil-modified.png" alt="Icon 1" class="icon-image" />
            <p class="icon-name">Darshil Sheth</p>
        </div>
        <div class="photo-icon">
            <img src="../assets/jasper-modified.png" alt="Icon 2" class="icon-image" />
            <p class="icon-name">Jasper Lieu</p>
        </div>
        <div class="photo-icon">
            <img src="../assets/nick.png" alt="Icon 3" class="icon-image" />
            <p class="icon-name">Nicholas Hoang</p>
        </div>
    </div>

    <div class="sample-text2">
        <p>Welcome to AutoChef! Enter your ingredients below and let us suggest some recipes for you!</p>
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
        recipes: []
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
<style>
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
  font-family: 'Roboto', sans-serif; /* Base font */
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  height: 100vh;
  margin: 0;
  background-color: #fff7e1; /* Soft off-white background */
  overflow-x: hidden;
}

.container {
  width: 85vw;
  max-width: 1200px;
  background-color: #fff;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  padding: 40px;
  justify-content: flex-start;
  box-sizing: border-box;
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  margin-bottom: 40px;
  background: linear-gradient(45deg, #FFB800, #FF6F00); /* Gradient from yellow to orange */
  border-radius: 50px;
  padding: 20px 40px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  transform: scale(1.05);
}

.header h1 {
  font-family: 'Poppins', sans-serif; /* Stylish, modern font */
  font-size: 3.5em;
  font-weight: 700;
  color: #fff;
  text-shadow: 4px 4px 12px rgba(0, 0, 0, 0.2);
  margin: 0;
  letter-spacing: 2px;
}

.logo {
  width: 90px;
  height: 90px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease-in-out;
}

.logo:hover {
  transform: rotate(360deg);
}

.sample-text,
.sample-text2 {
  font-family: 'Roboto', sans-serif;
  font-size: 1.25em;
  color: #333;
  margin-bottom: 40px;
  text-align: center;
  line-height: 1.6;
  letter-spacing: 0.5px;
}

.sample-text {
  font-weight: 500;
  color: #FF6F00;
}

.sample-text2 {
  font-weight: 300;
  color: #FFB800;
}

.input-section {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-bottom: 40px;
}

.input-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

input[type="text"] {
  width: 70%;
  padding: 12px 16px;
  font-size: 1.1em;
  font-weight: 500;
  border-radius: 30px;
  border: 2px solid #ddd;
  transition: border-color 0.3s, box-shadow 0.3s ease-in-out;
}

input[type="text"]:focus {
  border-color: #FFB800;
  box-shadow: 0 0 8px rgba(255, 184, 0, 0.6);
  outline: none;
}

#submit-btn {
  padding: 12px 25px;
  background-color: #FF6F00;
  color: white;
  font-size: 1.1em;
  font-weight: 600;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s ease-in-out;
}

#submit-btn:hover {
  background-color: #E65100;
  transform: scale(1.05);
}

.checkbox-item {
  display: flex;
  align-items: center;
  font-size: 1.1em;
  color: #333;
  margin-bottom: 12px;
}

.checkbox-item input {
  margin-right: 12px;
  accent-color: #FF6F00; /* Modern orange checkbox color */
  width: 20px;
  height: 20px;
  transition: transform 0.2s ease-in-out;
}

.checkbox-item input:hover {
  transform: scale(1.2); /* Slight scaling on hover */
}

.checkbox-item input:checked {
  background-color: #FFB800; /* Bright yellow for checked state */
  border-color: #FF6F00; /* Orange border when checked */
}

.recipes {
  display: flex;
  justify-content: space-around;
  gap: 20px;
  margin-top: 40px;
}

.recipe-box {
  width: 18%;
  padding: 15px;
  background-color: #FFFAE1;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.2s, box-shadow 0.2s ease-in-out;
  font-family: 'Roboto', sans-serif;
  font-size: 1.1em;
  font-weight: 400;
  color: #333;
}

.recipe-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
}

.photo-icons {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 40px;
}

.photo-icon {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 130px;
  height: 130px;
  border-radius: 20px;
  padding: 15px;
  background-color: #FF6F00; /* Vivid orange background */
  box-shadow: 0 6px 14px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
  font-family: 'Poppins', sans-serif;
}

.photo-icon:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 18px rgba(0, 0, 0, 0.15);
}

.icon-image {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  object-fit: cover;
  transition: transform 0.2s ease-in-out;
}

.icon-name {
  margin-top: 10px;
  font-size: 1.1em;
  font-weight: 600;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.icon-image:hover {
  transform: scale(1.1);
}

.checkboxes {
    display: flex;
    justify-content: space-around;
    margin-top: 5px;
  }
</style>