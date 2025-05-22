# 🧼 Clean Front-End Code Principles (No Frameworks)

A complete guide to writing clean, maintainable, and scalable front-end code using **HTML**, **CSS**, and **vanilla JavaScript** — no frameworks required.

---

## 📖 Table of Contents

1. [Use Semantic HTML](#-1-use-semantic-html)  
2. [Separate Structure, Style, and Behavior](#-2-separate-structure-style-and-behavior)  
3. [Use Consistent and Descriptive Naming (BEM)](#-3-use-consistent-and-descriptive-naming-bem)  
4. [Write Modular, Reusable CSS](#-4-write-modular-reusable-css)  
5. [Write Clean and Minimal JavaScript](#-5-write-clean-and-minimal-javascript)  
6. [Comment Why, Not What](#-6-comment-why-not-what)  
7. [Focus on Accessibility (a11y)](#-7-focus-on-accessibility-a11y)  
8. [Organize Files Logically](#-8-organize-files-logically)  
9. [Avoid Inline Code](#-9-avoid-inline-code)  
10. [Optimize for Performance](#-10-optimize-for-performance)  
11. [Final Checklist](#-11-final-checklist)  
12. [Using This Guide with docs.page](#-12-using-this-guide-with-docspage)  

---

## 🧱 1. Use Semantic HTML

```html
<!-- ❌ Bad -->
<div class="nav"><a href="/">Home</a></div>

<!-- ✅ Good -->
<nav><a href="/">Home</a></nav>
```

## 📐 2. Separate Structure, Style, and Behavior

```html
<!-- index.html -->
<link rel="stylesheet" href="styles.css">
<script src="main.js" defer></script>
<button id="clickBtn">Click Me</button>
```

```css
/* styles.css */
#clickBtn {
  background-color: #007bff;
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  font-size: 16px;
}
```

```js
// main.js
document.getElementById("clickBtn").addEventListener("click", () => {
  alert("Hello!");
});
```

## 🧱 3. Use Consistent and Descriptive Naming (BEM)

```html
<div class="card card--featured">
  <h2 class="card__title">Product Name</h2>
  <p class="card__description">Product description goes here.</p>
</div>
```

```css
.card {
  border: 1px solid #ccc;
  padding: 1rem;
  border-radius: 5px;
}
.card--featured {
  border-color: #007bff;
  background-color: #e6f0ff;
}
.card__title {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}
.card__description {
  font-size: 1rem;
  color: #555;
}
```

## 🧩 4. Write Modular, Reusable CSS

```css
:root {
  --primary-color: #007bff;
  --padding: 1rem;
}
.btn {
  padding: var(--padding);
  background-color: var(--primary-color);
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}
.btn--outline {
  background: transparent;
  border: 2px solid var(--primary-color);
  color: var(--primary-color);
}
```

```html
<button class="btn">Primary Button</button>
<button class="btn btn--outline">Outline Button</button>
```

## ⚙️ 5. Write Clean and Minimal JavaScript

```js
(() => {
  const button = document.querySelector("#toggleBtn");
  const box = document.querySelector("#contentBox");

  function toggleBox() {
    box.hidden = !box.hidden;
  }

  button.addEventListener("click", toggleBox);
})();
```

## 🧠 6. Comment Why, Not What

```js
// Use debounce to limit API calls when user types quickly
input.addEventListener("input", debounce(searchUsers, 300));
```

## ♿ 7. Focus on Accessibility (a11y)

```html
<button aria-pressed="false" id="likeBtn">Like</button>

<script>
  const btn = document.getElementById("likeBtn");
  btn.addEventListener("click", () => {
    const pressed = btn.getAttribute("aria-pressed") === "true";
    btn.setAttribute("aria-pressed", !pressed);
  });
</script>
```

## 📁 8. Organize Files Logically

```
/css
/js
/images
/index.html
```

## 🚫 9. Avoid Inline Code

```html
<!-- ❌ Avoid -->
<button style="color:red;" onclick="alert('Hi')">Click</button>

<!-- ✅ Use external files -->
```

## ⚡ 10. Optimize for Performance

```html
<script src="main.js" defer></script>
```

## ✅ 11. Final Checklist

- Semantic HTML used?  
- CSS and JS separated?  
- Naming consistent with BEM?  
- CSS modular and reusable?  
- JS clean and minimal?  
- Comments explain *why*?  
- Accessibility considered?  
- Files organized?  
- No inline styles or scripts?  
- Performance optimized?  

## 📚 12. Using This Guide with docs.page

1. Push your project with this README to a **public GitHub repo**.  
2. Visit [https://docs.page](https://docs.page) and connect your repo.  
3. Docs.page automatically builds and hosts your documentation site for free.

---

Thank you for reading! Feel free to contribute and improve these principles. 🚀
