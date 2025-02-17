document.addEventListener("DOMContentLoaded", () => {
    const themeToggle = document.getElementById("theme-toggle");
    const themeIcon = document.getElementById("theme-icon");
    const body = document.body;

    // Verificar si hay un tema guardado en localStorage
    if (localStorage.getItem("theme") === "dark") {
        body.classList.add("dark-theme");
        themeIcon.src = "assets/sun.png";
        themeIcon.alt = "Modo claro";
    }

    themeToggle.addEventListener("click", () => {
        if (body.classList.contains("dark-theme")) {
            body.classList.remove("dark-theme");
            themeIcon.src = "assets/moon.png";
            themeIcon.alt = "Modo oscuro";
            localStorage.setItem("theme", "light");
        } else {
            body.classList.add("dark-theme");
            themeIcon.src = "assets/sun.png";
            themeIcon.alt = "Modo claro";
            localStorage.setItem("theme", "dark");
        }
    });
});


document.addEventListener("DOMContentLoaded", () => {
    const circles = document.querySelectorAll(".circle");

    circles.forEach(circle => {
        circle.addEventListener("click", () => {
            const infoBox = circle.nextElementSibling; // Encuentra la caja de info
            infoBox.style.display = infoBox.style.display === "block" ? "none" : "block";
        });
    });
});