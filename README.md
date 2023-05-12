# Capsolver
Capsolver official javascript library

## Supported CAPTCHA types:
- HCaptcha
- FunCaptcha
- Geetest
- ReCaptchaV2
- ReCaptchav3


## Installation

You don't need this source code, just the requests and apis.

## Usage ( Example, Proxyless )
First provide your api key, to send the requests.
```bash
let capsolver_api_key = "Your API key";
```
Then, send the requests with needed arguments. Replace variables ( let var ) with your data.
```javascript
let taskType = "TaskType";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Fehler beim Erstellen der Aufgabe:", error);
  });
```

## CreateTask with proxy ( Example )
To add proxies, to your createTask request, add this as payload ( data ) arguments.
```javascript
"proxyType": "http",
"proxyAddress":"8.8.8.8",
"proxyPort":8080
```
## Supported Proxy types:
- Http
- Https
- Socks4
- Socks5
## createTask ( Example ):
This code, creates an task with proxies.
```javascript
let taskType = "TaskType";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    "proxyType": "http",
    "proxyAddress":"8.8.8.8",
    "proxyPort":8080,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creating task", error);
  });
```

## Hcaptcha Solver
```javascript
let taskType = "HCaptchaTaskProxyLess ";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creating task:", error);
  });
```

## FunCaptcha Solver
```javascript
let taskType = "FunCaptchaTaskProxyLess";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creating task:", error);
  });
```

## GeeCaptcha Solver
```javascript
let taskType = "GeeTestTaskProxyLess";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creating task:", error);
  });
```
## ReCaptchaV2 Solver
```javascript
let taskType = "ReCaptchaV2TaskProxyLess";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creting task:", error);
  });
```
## ReCaptchaV3 Solver
```javascript
let taskType = "ReCaptchaV3EnterpriseTaskProxyLess";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creting task:", error);
  });
```
## MTCaptcha Solver
```javascript
let taskType = "MTCaptcha";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    "proxy": "ip:port:user:pass",
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creting task:", error);
  });
```
## ReCaptchaV2 Solver
```javascript
let taskType = "ReCaptchaV2TaskProxyLess";
let siteUrl = "SiteURL";
let sitekey = "6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-";

let createTaskData = {
  clientKey: capsolver_api_key,
  appId: "Your AppID",
  task: {
    type: taskType,
    websiteURL: siteUrl,
    websiteKey: sitekey,
    userAgent:
      "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36",
  },
};

fetch("https://api.capsolver.com/createTask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(createTaskData),
})
  .then((response) => response.json())
  .then((data) => {
    let taskId = data.taskId;

    let getTaskResultData = {
      clientKey: capsolver_api_key,
      taskId: taskId,
    };

    fetch("https://api.capsolver.com/getTaskResult", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(getTaskResultData),
    })
      .then((response) => response.json())
      .then((data) => {
        let gRecaptchaResponse = data.solution.gRecaptchaResponse;

        console.log("gRecaptchaResponse:", gRecaptchaResponse);
      })
      .catch((error) => {
        console.error("Error while creating task:", error);
      });
  })
  .catch((error) => {
    console.error("Error while creting task:", error);
  });
```
## Informations:
To send other requests or types of captchas, read the top and replace the TaskType with the provided one you want.
Please keep in mind, some tasks have extra data like RqData, but if you have to use that you know how to code :D
