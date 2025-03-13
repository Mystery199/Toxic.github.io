function login() {
    let email = document.getElementById("email").value;
    localStorage.setItem("user", email);
    window.location.reload();
}

function logout() {
    localStorage.removeItem("user");
    window.location.reload();
}

function earnCoins() {
    let coins = parseInt(localStorage.getItem("coins") || 0);
    coins += 1;
    localStorage.setItem("coins", coins);
    document.getElementById("coins").innerText = coins;
}

function redeemCode() {
    let code = prompt("Enter Redeem Code:");
    if (code === "FREE100") {
        let coins = parseInt(localStorage.getItem("coins") || 0);
        coins += 100;
        localStorage.setItem("coins", coins);
        document.getElementById("coins").innerText = coins;
        alert("Code Redeemed!");
    } else {
        alert("Invalid Code!");
    }
}
