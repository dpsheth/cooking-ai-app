<template>
    <div class="container">
        <!-- Input Section -->
        <div class="input-section">
            <h2>Input</h2>
            <input type="text" placeholder="Enter ingredients or preferences..." class="input-box">
            <button class="chatbot-btn">Chatbot?</button>
            <div class="dietary-restrictions">
                <h3>Dietary Restrictions:</h3>
                <button class="dietary-btn">Vegan</button>
                <button class="dietary-btn">Nut-Free</button>
                <button class="dietary-btn">Gluten-Free</button>
                <!-- Add more dietary options as needed -->
            </div>
        </div>

        <!-- Output Section -->
        <div class="output-section">
            <h2>Output</h2>
            <div class="output-content">
                <h3>Ingredients</h3>
                <ul class="ingredients-list">
                    <!-- Ingredients will be populated here -->
                    <li>Example Ingredient 1</li>
                    <li>Example Ingredient 2</li>
                </ul>

                <h3>Recipe Instructions</h3>
                <p class="recipe-instructions">
                    <!-- Recipe instructions will be populated here -->
                    Follow the steps to complete your recipe.
                </p>
            </div>
            <!-- Action Icons -->
            <div class="action-icons">
                <button class="icon-btn">🔄</button>
                <button class="icon-btn">💾</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'RecipeGenerator'
};
</script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

.container {
    display: flex;
    gap: 2rem;
    padding: 2rem;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.input-section, .output-section {
    flex: 1;
    padding: 1rem;
}

.input-section {
    border-right: 2px solid #ccc;
}

.input-section h2, .output-section h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
}

.input-box {
    width: 100%;
    padding: 0.5rem;
    margin-bottom: 1rem;
    border-radius: 4px;
    border: 1px solid #ccc;
}

.chatbot-btn {
    display: inline-block;
    padding: 0.5rem 1rem;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    margin-bottom: 1rem;
}

.dietary-restrictions h3 {
    margin-top: 1rem;
    margin-bottom: 0.5rem;
}

.dietary-btn {
    display: inline-block;
    padding: 0.5rem;
    margin: 0.2rem;
    background-color: #ddd;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.output-section {
    position: relative;
}

.output-content h3 {
    font-size: 1.2rem;
    margin-top: 1rem;
}

.ingredients-list {
    list-style: none;
    margin: 1rem 0;
}

.recipe-instructions {
    margin-top: 1rem;
    line-height: 1.5;
}

.action-icons {
    position: absolute;
    bottom: 1rem;
    right: 1rem;
    display: flex;
    gap: 1rem;
}

.icon-btn {
    font-size: 1.5rem;
    background: none;
    border: none;
    cursor: pointer;
}
</style>
