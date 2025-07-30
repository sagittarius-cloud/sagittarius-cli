# Sagittarius CLI

A powerful command-line interface for creating, managing, and deploying applications with integrated CI/CD support.

## Features

- 🔐 **Secure Authentication** - Login with token storage in system keychain
- 🚀 **App Management** - Create, deploy, update, and monitor applications  
- 🔄 **CI/CD Integration** - Built-in support for GitHub Actions and GitLab CI
- 📊 **Real-time Monitoring** - Watch app status and stream logs
- ⚙️ **Configuration Management** - Flexible config file support
- 🛡️ **Cross-platform** - Works on Windows, macOS, and Linux

## Installation

### Global Installation (Recommended)

```bash
npm install -g sagittarius-cli
```

### From Source

```bash
git clone https://github.com/yourusername/sagittarius-cli.git
cd sagittarius-cli
npm install
npm link
```

## Quick Start

1. **Login to your account**
   ```bash
   sagittarius login
   ```

2. **Create a new application**
   ```bash
   sagittarius create my-app
   cd my-app
   ```

3. **Deploy your application**
   ```bash
   sagittarius deploy
   ```

## Commands

### Authentication

```bash
# Login with username/password
sagittarius login

# Login with API token
sagittarius login --token YOUR_TOKEN

# Check current user
sagittarius whoami

# Logout
sagittarius logout
```

### Application Management



### Configuration



### CI/CD Integration



## Configuration Files

Sagittarius CLI supports configuration files in your project root:



## CI/CD Integration

### GitHub Actions

```yaml
name: Deploy to Sagittarius
on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          
      - name: Install Sagittarius CLI
        run: npm install -g sagittarius-cli
        
      - name: Deploy
        run: sagittarius ci-deploy --environment production
        env:
          SAGITTARIUS_TOKEN: ${{ secrets.SAGITTARIUS_TOKEN }}
```



## Environment Variables

- `SAGITTARIUS_TOKEN` - API token for authentication (used in CI/CD)
- `SAGITTARIUS_API_URL` - API base URL (default: https://sagittaireapi.online)

## Token Storage

Sagittarius CLI securely stores authentication tokens:

- **Desktop**: System keychain (macOS Keychain, Windows Credential Store, Linux Secret Service)
- **CI/CD**: Environment variables or secure file storage
- **Fallback**: Encrypted file in `~/.sagittarius/`

### Get application details
```bash
sagittarius apps --id 118
```

### Watch application details
```bash
sagittarius apps --id 118 --watch
```

### List container apps
```bash
sagittarius apps list --app-type container-apps
```

### Follow application logs
```bash
sagittarius logs my-app --follow
```

### Deploy with custom config
```bash
sagittarius deploy --config ./deploy.yml --environment production
```

## Troubleshooting

### Authentication Issues
```bash
# Check if logged in
sagittarius whoami

# Re-login if token expired
sagittarius logout
sagittarius login
```

### Permission Issues
```bash
# On Unix systems, ensure executable permissions
chmod +x /usr/local/bin/sagittarius
```

### CI/CD Issues
```bash
# Verify token is set
echo $SAGITTARIUS_TOKEN

# Use ci-deploy command specifically
sagittarius ci-deploy --environment production
```

## Support

- 📖 Documentation: https://docs.sagittarius.dev
- 🐛 Issues: https://github.com/yourusername/sagittarius-cli/issues
- 💬 Discord: https://discord.gg/sagittarius

## License

MIT License - see [LICENSE](LICENSE) file for details.
