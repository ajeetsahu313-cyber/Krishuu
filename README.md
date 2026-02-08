# Krishuu
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be My Girlfriend? ❤️</title>

<link rel="stylesheet" href="styles.css">
</head>

<body>

<div class="container">
    <div class="card">

        <h1>Will You Be My Girlfriend? ❤️</h1>

        <div class="buttons">
            <button id="yesBtn">Yes 😍</button>
            <button id="noBtn">No 😢</button>
        </div>

    </div>
</div>

<script src="script.js"></script>

</body>
</html>
body {
    margin:0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg,#ff9a9e,#fecfef);
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
}

.card {
    background:white;
    padding:40px;
    border-radius:20px;
    box-shadow:0 10px 40px rgba(0,0,0,0.3);
    text-align:center;
}

h1 {
    color:#ff1744;
    margin-bottom:30px;
}

.buttons {
    display:flex;
    gap:20px;
    justify-content:center;
}

button {
    padding:15px 40px;
    font-size:18px;
    border:none;
    border-radius:40px;
    cursor:pointer;
}

#yesBtn {
    background:#ff1744;
    color:white;
}

#noBtn {
    background:#ccc;
}
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

let scale = 1;

// Make NO button run away
document.addEventListener("mousemove", (e) => {

    const rect = noBtn.getBoundingClientRect();

    const dist =
        Math.abs(e.clientX - rect.left) +
        Math.abs(e.clientY - rect.top);

    if (dist < 120) {

        const maxX = window.innerWidth - rect.width;
        const maxY = window.innerHeight - rect.height;

        const randX = Math.random() * maxX;
        const randY = Math.random() * maxY;

        noBtn.style.position = "fixed";
        noBtn.style.left = randX + "px";
        noBtn.style.top = randY + "px";

        // Grow YES button
        scale += 0.15;
        yesBtn.style.transform = `scale(${scale})`;
    }
});

// YES click action
yesBtn.addEventListener("click", () => {
    document.body.innerHTML = `
        <div style="
            height:100vh;
            display:flex;
            justify-content:center;
            align-items:center;
            font-size:40px;
            color:white;
            background:#ff1744;
            text-align:center;
        ">
            ❤️ Yay!!! I knew it 😍 ❤️
        </div>
    `;
});
