// User Login System
function login() {
    let username = document.getElementById("username").value;
    if (username) {
        localStorage.setItem("username", username);
        localStorage.setItem("coins", 0);
        showDashboard();
    } else {
        alert("Please enter a username!");
    }
}

// Show Dashboard After Login
function showDashboard() {
    document.getElementById("login-page").style.display = "none";
    document.getElementById("dashboard").style.display = "block";
    document.getElementById("coins").innerText = localStorage.getItem("coins");
}

// Earn Coins System
function earnCoins() {
    let coins = parseInt(localStorage.getItem("coins")) + 10;
    localStorage.setItem("coins", coins);
    document.getElementById("coins").innerText = coins;
}

// Redeem Code System
function redeemCode() {
    let code = prompt("Enter Redeem Code:");
    if (code === "TOXIC100") {
        let coins = parseInt(localStorage.getItem("coins")) + 100;
        localStorage.setItem("coins", coins);
        document.getElementById("coins").innerText = coins;
        alert("Redeem successful! +100 Coins added.");
    } else {
        alert("Invalid Redeem Code!");
    }
}

// AFK System (Auto Earn Coins)
function startAFK() {
    alert("AFK Mode started! You will earn coins automatically.");
    setInterval(() => {
        let coins = parseInt(localStorage.getItem("coins")) + 5;
        localStorage.setItem("coins", coins);
        document.getElementById("coins").innerText = coins;
    }, 5000);
}

// Logout System
function logout() {
    localStorage.clear();
    document.getElementById("dashboard").style.display = "none";
    document.getElementById("login-page").style.display = "block";
}
