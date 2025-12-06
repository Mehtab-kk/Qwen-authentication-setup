# Fix Error: **"Refresh token expired or invalid (API Error: 401)"**  
Qwen CLI + Claude-Code-Router Full Reset Guide

Below are the correct steps to fix the Qwen authentication error and reconnect it with Claude-Code-Router (CCR).  
Written in simple Roman English, step-by-step.


## ✅ step 1
first uninstall qwen code 

```

npm uninstall -g @qwen-code/qwen-code

```

## ✅ Step 2 — Reinstall Qwen CLI

Install latest Qwen CLI command:

```

npm install -g @qwen-code/qwen-code@latest

```

## ✅ Step 3 — Authenticate Qwen

Run:

```

qwen

```

Then authenticate:

```

/auth

```


Browser will open →
Select or add your Qwen account (working one) →
Login →
After success → Close the terminal.

## ✅ Step 4 — Get Your New Qwen Access Token

Press Windows + R

Type:

```
.qwen

```

Press Enter

Open file:

oauth_creds.json


(open in VS Code)

Inside you will see:

```
{
  "access_token": "YOUR_QWEN_ACCESS_TOKEN_HERE",
  "token_type": "Bearer",
  "refresh_token": "YOUR_QWEN_REFRESH_TOKEN_HERE",
  "resource_url": "portal.qwen.ai",
  "expiry_date": 1764876220290
}

```
👉 Copy access_token value.

## ✅ Step 5 — Add Qwen Token into Claude-Code-Router

Press Windows + R

Type:

```
.claude-code-router
```

Press Enter

Open:

config.json


(in VS Code)

Find:

"api_key": ""


Replace it with your Qwen access token:

"api_key": "YOUR_QWEN_ACCESS_TOKEN_HERE"


Save & close the file.

✅ Step 6 — Restart & Test CCR

Open PowerShell or CMD and run:



```

ccr restart

```

then:

```

ccr code

```

Send (Any sms for test):

```

hello

```

If **successful,** you will see reply like:

```

Hello, I am Claude...

```

🎉 Done! Your Qwen + Claude setup is now fixed.

**Best of luck!



