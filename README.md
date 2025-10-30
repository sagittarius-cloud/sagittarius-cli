<h1 align="center">✨ Sagittarius CLI 🚀</h1>
<p align="center">
	<img src="https://img.shields.io/badge/CLI-Node.js-green?logo=node.js" alt="Node.js CLI"/>
	<img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT License"/>
</p>


---

## 📦 Download & Install

⬇️ Download the latest stable release from the [Sagittarius repository](#) and follow the instructions below.

---


---

## 🛠️ Commands

Use the command <code>sag</code> or <code>sagittarius</code> in your terminal.


---

### 🔑 Login

> Sagittarius CLI uses a simple client architecture to connect with your account.<br>✨ <b>Service account login is coming soon!</b>


#### 👤 Login with Credentials
Login using your username and password:

```bash
sag login -u <your_username> -p <your_password>
```


<details>
<summary>Sample output</summary>

<pre>
🔐 Starting login process...
✅ Successfully logged in as your_username
🏢 Organizations: your_username's Default Organization
</pre>
</details>


#### 🪪 Login with Token
Login directly using your API token:

```bash
sag login -t <your_token>
```


🔗 Get your token at: [Sagittarius Profile](https://sagittair.io/profile)


👀 Check your account info:

```bash
sag whoami
```

---


---

## 📱 Manage Applications

> 🚀 Create, list, restart, and update your apps easily!


###	   Create an Application

To create an application, first create your artifact yaml file containing the configuration of the
app you want to deploy. Here is an example for a Container App artifact file.

First, create a new file in any directory called `app.yml` and add to it the following data:

```yaml
app:
  name: "Lawful Koala"
  description: "démo"
  organization: 1
  server_id: 1
  network_id: 2
  repo_url: "https://github.com/arka-cell/test_env"
  github_token: "ghp_xxxxxxxxxxxxxxxxx"
  dockerfile: "./Dockerfile"
  replicas: 1
  instance: "nano"
  ingress: "1"
  exposed_port: "9998"
  code_environment: "github"
  code_environment_username: ""
  add_workflow: 1
  environment_variables:
    POSTGRES_HOST: "POSTGRES_HOST"
    POSTGRES_DB: "postgres"
    POSTGRES_PORT: "5007"
    POSTGRES_PASSWORD: "postgres"
    POSTGRES_USER: "postgres"
  app_type: "container-app"

```

Once you created your file and your repository contains the necessary code and Dockerfile, run the following command:

```shell
sag apps create --file=$(pwd)/app.yml
```

This will create your app, while the deployment will take depending on the build and startup time of your app.

### 📋 List Applications

🔎 Show all your applications:

```bash
sag apps list
```


🔎 Show only container-apps:

```bash
sag apps list --app-type=container-app
```


🔎 Show all apps (any type):

```bash
sag apps list --app-type=all
```


### 🔄 Restart Applications

♻️ Restart your app to deploy new code changes from your repository:

```bash
sag restart --id=<app_id>
```

### 📺 Applications Logs


### 🆘 Help

❓ See all available app management commands:

```bash
sag apps --help
# or
sag apps -h
```

---


---

## 💡 Tips & Tricks

✨ Use <code>sag whoami</code> to check your current user and organizations.<br>
🔑 Use <code>sag login -t &lt;token&gt;</code> for quick authentication in CI/CD pipelines.<br>
📋 Use <code>sag apps list --app-type=all</code> to see every app you have access to.

---


---

## 🌐 Manage Networks

🔗 List all networks:
```bash
sag networks list
```

🔗 Get a specific network:
```bash
sag networks get --id=<network_id>
```


---

## 🏢 Manage Organizations

👥 List organizations:
```bash
sag organizations list
```

👁️‍🗨️ Get an organization:
```bash
sag organizations get --id=<org-id>
```

---

<p align="center">Made with ❤️ by the <b>Sagittarius</b> team</p>
