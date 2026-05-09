# Render Deployment Guide for booth_backend

## ✅ Prerequisites Complete
All configuration files are ready for deployment!

## 🚀 Deploy on Render

### Option 1: Using render.yaml (Blueprint)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Ready for Render deployment"
   git push origin master
   ```

2. **Deploy on Render**
   - Go to https://dashboard.render.com
   - Click "New +" → "Blueprint"
   - Connect your GitHub repository (vikas90244/vApp)
   - Render will automatically detect render.yaml
   - Click "Apply" - it will create both the web service and PostgreSQL database
   - Wait for deployment to complete

3. **Set Required Environment Variables** (in Render dashboard after deployment)
   - `ALLOWED_HOSTS`: Add your Render URL (e.g., `booth-backend.onrender.com`)
   - `CORS_ALLOWED_ORIGINS`: Add your frontend URL (e.g., `https://your-frontend.onrender.com`)

### Option 2: Manual Setup

1. **Push to GitHub** (same as above)

2. **Create PostgreSQL Database**
   - Click "New +" → "PostgreSQL"
   - Name: `booth-db`
   - Click "Create Database"
   - Save the connection details

3. **Create Web Service**
   - Click "New +" → "Web Service"
   - Connect your GitHub repo (vikas90244/vApp)
   - Root Directory: `booth_backend`
   - Name: `booth-backend`
   - Environment: `Python 3`
   - Build Command: `pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate`
   - Start Command: `gunicorn booth_backend.wsgi:application`

4. **Add Environment Variables**
   - `DEBUG`: `False`
   - `SECRET_KEY`: (Click "Generate" to auto-generate)
   - `ALLOWED_HOSTS`: `your-service.onrender.com`
   - `CORS_ALLOWED_ORIGINS`: `https://your-frontend.onrender.com`
   - `DB_ENGINE`: `django.db.backends.postgresql`
   - `DB_NAME`: (from PostgreSQL dashboard)
   - `DB_USER`: (from PostgreSQL dashboard)
   - `DB_PASSWORD`: (from PostgreSQL dashboard)
   - `DB_HOST`: (from PostgreSQL dashboard)
   - `DB_PORT`: `5432`

5. **Deploy** - Click "Create Web Service"

## 📝 After Deployment

1. Your backend will be available at: `https://booth-backend.onrender.com`
2. Test API endpoints: `https://booth-backend.onrender.com/api/`
3. Update frontend to use the new backend URL

## ⚠️ Important Notes

- Free tier services sleep after 15 minutes of inactivity
- First request after sleep may take 30-60 seconds
- PostgreSQL free tier has 90-day expiration
- Update ALLOWED_HOSTS and CORS_ALLOWED_ORIGINS with actual domains after deployment
