# Installation and expiration

# Fix Error: **"Refresh token expired or invalid (API Error: 401)"**  
Qwen CLI + Claude-Code-Router Full Reset Guide

Below are the correct steps to fix the Qwen authentication error and reconnect it with Claude-Code-Router (CCR).  
Written in simple Roman English, step-by-step.



## ✅ Step 1  Install Qwen CLI

Install latest Qwen CLI command:

```

npm install -g @qwen-code/qwen-code@latest

```

## ✅ Step 3  Authenticate Qwen

Run:(terminal)

```

qwen

```

Then authenticate:

```

/auth

```


Browser will open →
Select or add your Qwen account (working one) →
Login → After success
return to terminal and send any prompt qwen give you response (as give gemini or claude) 
Close the terminal.


## ✅ Step 4

 **Create the Folders**
 
Paste this into PowerShell:

```

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude-code-router", "$env:USERPROFILE\.claude"

```
press enter

## ✅ Step 5

 Press **window + R**
 
Type:

```
.qwen

```

Press Enter

Open file:

oauth_creds.json

(open in VS Code)

Inside you will see:(in file oauth_creds.json )

```
{
  "access_token": "YOUR_QWEN_ACCESS_TOKEN_HERE", //just see 
  "token_type": "Bearer",                    // not a command
  "refresh_token": "YOUR_QWEN_REFRESH_TOKEN_HERE", 
  "resource_url": "portal.qwen.ai",
  "expiry_date": 1764876220290
}

```
👉 Copy access_token value.(YOUR_QWEN_ACCESS_TOKEN_HERE)


  

## ✅ Step 6
open terminal run below command 

**Before Enter**

👉find "api_key": "YOUR_QWEN_ACCESS_TOKEN_HERE"

Here you add ACCESS_TOKEN  (you have already copy in step 5)

```

@"
{  
  "LOG": true,  
  "LOG_LEVEL": "info",  
  "HOST": "127.0.0.1",  
  "PORT": 3456,  
  "API_TIMEOUT_MS": 600000,  
  "Providers": [  
    {  
      "name": "qwen",  
      "api_base_url": "https://portal.qwen.ai/v1/chat/completions",  
      "api_key": "YOUR_QWEN_ACCESS_TOKEN_HERE",  
      "models": [  
        "qwen3-coder-plus",  
        "qwen3-coder-plus",  
        "qwen3-coder-plus"  
      ]  
    }  
  ],  
  "Router": {  
    "default": "qwen,qwen3-coder-plus",  
    "background": "qwen,qwen3-coder-plus",  
    "think": "qwen,qwen3-coder-plus",  
    "longContext": "qwen,qwen3-coder-plus",  
    "longContextThreshold": 60000,  
    "webSearch": "qwen,qwen3-coder-plus"  
  }  
}
"@ | Out-File -FilePath "$env:USERPROFILE\.claude-code-router\config.json" -Encoding UTF8

```

Then **Enter**


## ✅ Step 6 Test

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



