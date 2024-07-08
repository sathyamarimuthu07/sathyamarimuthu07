html
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crowdfunding App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Crowdfunding Projects</h1>
    </header>
    <main>
        <div id="projects"></div>
    </main>
    <footer>
        <p>&copy; 2024 Crowdfunding App</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>

js

const projects = [
  {
    id: 1,
    title: "Project A",
    description: "Description of Project A",
    goal: 1000,
    pledged: 500,
  },
  {
    id: 2,
    title: "Project B",
    description: "Description of Project B",
    goal: 2000,
    pledged: 1500,
  },
  {
    id: 3,
    title: "Project C",
    description: "Description of Project C",
    goal: 1500,
    pledged: 1300,
  },
];

function renderProjects() {
  const projectContainer = document.getElementById("projects");
  projectContainer.innerHTML = "";

  projects.forEach((project) => {
    const projectElement = document.createElement("div");
    projectElement.className = "project";
    projectElement.innerHTML = `
            <h2>${project.title}</h2>
            <p>${project.description}</p>
            <p>Goal: $${project.goal}</p>
            <p>Pledged: $${project.pledged}</p>
            <input type="number" min="1" placeholder="Amount" id="pledge-${project.id}">
            <button onclick="pledge(${project.id})">Pledge</button>
        `;
    projectContainer.appendChild(projectElement);
  });
}

function pledge(projectId) {
  const amount = document.getElementById(`pledge-${projectId}`).value;
  const project = projects.find((p) => p.id === projectId);
  if (amount && project) {
    project.pledged += parseInt(amount);
    renderProjects();
  }
}

document.addEventListener("DOMContentLoaded", () => {
  renderProjects();
});




<!---
sathyamarimuthu07/sathyamarimuthu07 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
