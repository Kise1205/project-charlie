# 🎮 CIS 376 – DEV CHARLIE PROJECT

Welcome to the **Dev Charlie Project**, a collaborative web application created for the CIS 376 — Web Development course.  
This project collects and displays student-built games from the class, allowing users to browse, sort, and launch each game.

---

## 👥 Team Information

**Team Name:** *Team 3*

**Members:**

| Student | Name |
|---------|----------------|
| Member 1 | David Burls |
| Member 2 | Nhu Tran |
| Member 3 | Thuan Nguyen |

---

## 🧠 Product Overview

**Product Name:** *Class Game Gallery*  
**Description:**  
A simple, user-friendly web application that displays games created by CIS 376 students. Users can view game thumbnails, open the live game, or explore its GitHub repository. The app allows sorting of games alphabetically for easier browsing.

---

## 🚀 How to View
**Live Site:** [Class Game Gallery](https://kise1205.github.io/project-charlie/)  
**Source Code:** [GitHub Repo](https://github.com/Kise1205/project-charlie)

---

## 🧑‍💻 User Story & Scenario

> **As a** student or visitor exploring CIS 376 projects,  
> **I want** to browse and access class-created games in one place,  
> **so that** I can quickly discover, play, and learn from my classmates’ work.

---

## ✅ Validation Results

All pages were validated for **HTML** and **accessibility**:

| Validator | Status |
|-----------|--------|
| **Nu HTML Checker** | ✅ Passed with no major errors |
| **WAVE Accessibility Tool** | ✅ Passed (no contrast or accessibility failures) |

---

## 🧱 Code Base Overview

The project is built using **HTML, CSS, JavaScript ES Modules, and Bootstrap 5**.  
JavaScript modules are used to separate data storage and functional logic for clarity and maintainability.

### 📌 Data Flow & Architecture

- **data.js**  
  Stores a shared array of student game objects, including name, repo link, app link, and thumbnail.

- **script.js**  
  Imports the dataset and dynamically renders cards to the UI.  
  Users can sort the game list alphabetically (A → Z / Z → A).

- **index.html**  
  Serves as the entry point and loads module scripts.

---

## 💻 Code Snippet (ES Module Import)

```javascript
// app.js
function renderCards() {
  const sorted = sortData(stuData);
  grid.innerHTML = '';

  sorted.forEach(item => {
    const col = document.createElement('div');
    col.className = 'col-12 col-sm-6 col-lg-4';

    col.innerHTML = `
      <div class="card h-100">
        <img class="card-img-top" src="${item.img}" alt="${item.name}">
        <div class="card-body">
          <h5 class="card-title">${item.name}</h5>
          <div class="d-grid gap-2">
            <a class="btn btn-primary" href="${item.app}" target="_blank">Play</a>
            <a class="btn btn-outline-secondary" href="${item.repo}" target="_blank">Repo</a>
          </div>
        </div>
      </div>
    `;

    grid.appendChild(col);
  });
}
```
### Explaination
renderCards() helps reder HTML cards dynamically.

```javascript
function sortData(data) {
  return data.slice().sort((a, b) =>
    sortOrder === 'asc'
      ? a.name.localeCompare(b.name)   // Sort A → Z
      : b.name.localeCompare(a.name)   // Sort Z → A
  );
}
```
### Explaination
sortData() sorts the array of game names either A → Z or Z → A using localeCompare() for accurate alphabetical sorting.

---

## Project Root
│ index.html
│ README.md
│
├─ scripts
│   ├─ data.js        # Stores class game data
│   └─ script.js         # Rendering + sorting logic (ES module)
│
├─ styles
   └─ styles.css     # Custom styling



