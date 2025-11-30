# 🔄 Admin Panel CI/CD Setup Guide

## 📋 GitHub Secrets Required

Go to your GitHub repository: **Settings → Secrets and variables → Actions**

### Add These Secrets:

#### 1. DOCKER_HUB_TOKEN
```
Value: Your Docker Hub access token
```

#### 2. VITE_BACKEND_URL
```
Value: Your backend API URL
Production: https://api.yourdomain.com
Development: http://localhost:4000
```

---

## 🚀 How It Works

### Triggers:
- ✅ Push to `master` branch
- ✅ Pull request to `master`
- ✅ Manual trigger

### Pipeline Steps:
1. Checkout code
2. Install dependencies
3. Run ESLint
4. Build React app
5. Build Docker image (React + Nginx)
6. Push to Docker Hub
7. Test container
8. **Security scan with Trivy**

### Tags Generated:
- `latest`
- `v1.0.X`
- `abc1234` (commit SHA)

---

## 🔒 Security

- ✅ Trivy vulnerability scanning
- ✅ Reports HIGH and CRITICAL issues

---

## 📦 Deployment

```bash
docker pull arbabmustafa/forever-admin:latest
docker run -d -p 80:80 arbabmustafa/forever-admin:latest
```

---

**Setup Time:** ~5 minutes  
**Build Time:** ~3-4 minutes
