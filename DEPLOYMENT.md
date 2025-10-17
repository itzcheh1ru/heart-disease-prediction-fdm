# 🚀 Deployment Guide
## Heart Disease Prediction System

This guide provides step-by-step instructions for deploying the Heart Disease Prediction System to various platforms.

---

## 🌐 **Live Deployment**

**Current Production URL**: https://heart-disease-prediction-fdm-production.up.railway.app

### 🚂 **Railway.app Deployment**

Railway.app is the current deployment platform. Here's how to deploy:

1. **Connect Repository**
   - Sign up at [Railway.app](https://railway.app)
   - Connect your GitHub repository
   - Select the main branch

2. **Environment Variables**
   ```bash
   DEBUG=False
   SECRET_KEY=your-production-secret-key
   ALLOWED_HOSTS=heart-disease-prediction-fdm-production.up.railway.app
   ```

3. **Database Setup**
   - Railway automatically provides PostgreSQL
   - Run migrations: `python manage.py migrate`
   - Create superuser: `python manage.py createsuperuser`

4. **Static Files**
   - Railway handles static file serving
   - No additional configuration needed

---

## 🐳 **Docker Deployment**

### **Dockerfile**
```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

### **Docker Compose**
```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "8000:8000"
    environment:
      - DEBUG=False
      - SECRET_KEY=your-secret-key
    volumes:
      - .:/app
```

---

## ☁️ **Cloud Platform Deployment**

### **Heroku Deployment**

1. **Install Heroku CLI**
2. **Create Heroku App**
   ```bash
   heroku create your-app-name
   ```

3. **Environment Variables**
   ```bash
   heroku config:set DEBUG=False
   heroku config:set SECRET_KEY=your-secret-key
   ```

4. **Deploy**
   ```bash
   git push heroku main
   heroku run python manage.py migrate
   ```

### **AWS Deployment**

1. **Elastic Beanstalk**
   - Create new application
   - Upload source code
   - Configure environment variables
   - Deploy application

2. **EC2 Instance**
   - Launch EC2 instance
   - Install dependencies
   - Configure nginx
   - Set up SSL certificate

---

## 🔧 **Production Configuration**

### **Settings Configuration**
```python
# Production settings
DEBUG = False
ALLOWED_HOSTS = ['your-domain.com', 'your-app.railway.app']
SECRET_KEY = os.environ.get('SECRET_KEY')

# Database
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('DATABASE_NAME'),
        'USER': os.environ.get('DATABASE_USER'),
        'PASSWORD': os.environ.get('DATABASE_PASSWORD'),
        'HOST': os.environ.get('DATABASE_HOST'),
        'PORT': os.environ.get('DATABASE_PORT'),
    }
}

# Static files
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
```

### **Security Headers**
```python
# Security settings
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'
SECURE_HSTS_SECONDS = 31536000
SECURE_HSTS_INCLUDE_SUBDOMAINS = True
SECURE_HSTS_PRELOAD = True
```

---

## 📊 **Performance Optimization**

### **Database Optimization**
- Use database indexing
- Implement query optimization
- Set up database connection pooling
- Configure database caching

### **Static Files**
- Use CDN for static files
- Enable gzip compression
- Implement browser caching
- Optimize images and assets

### **Caching Strategy**
```python
# Redis caching
CACHES = {
    'default': {
        'BACKEND': 'django_redis.cache.RedisCache',
        'LOCATION': 'redis://127.0.0.1:6379/1',
        'OPTIONS': {
            'CLIENT_CLASS': 'django_redis.client.DefaultClient',
        }
    }
}
```

---

## 🔍 **Monitoring & Logging**

### **Error Tracking**
- Set up Sentry for error tracking
- Configure logging levels
- Monitor application performance
- Set up alerts for critical issues

### **Health Checks**
```python
# Health check endpoint
def health_check(request):
    return JsonResponse({'status': 'healthy'})
```

---

## 🔐 **Security Configuration**

### **SSL/TLS**
- Enable HTTPS
- Configure SSL certificates
- Set up secure headers
- Implement CSRF protection

### **Environment Variables**
```bash
# Production environment variables
DEBUG=False
SECRET_KEY=your-super-secret-key
DATABASE_URL=postgresql://user:password@host:port/dbname
ALLOWED_HOSTS=your-domain.com
```

---

## 📈 **Scaling Considerations**

### **Horizontal Scaling**
- Use load balancers
- Implement session management
- Configure database replication
- Set up auto-scaling

### **Vertical Scaling**
- Optimize server resources
- Implement caching strategies
- Use database optimization
- Monitor resource usage

---

## 🚨 **Troubleshooting**

### **Common Issues**

1. **Static Files Not Loading**
   - Check STATIC_ROOT configuration
   - Verify static file collection
   - Check web server configuration

2. **Database Connection Issues**
   - Verify database credentials
   - Check network connectivity
   - Verify database permissions

3. **Environment Variable Issues**
   - Check variable names
   - Verify variable values
   - Ensure proper escaping

### **Debug Commands**
```bash
# Check Django configuration
python manage.py check --deploy

# Collect static files
python manage.py collectstatic

# Run database migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser
```

---

## 📞 **Support**

For deployment issues:
- Check application logs
- Verify environment variables
- Test database connectivity
- Review server configuration

---

**Happy Deploying! 🚀**
