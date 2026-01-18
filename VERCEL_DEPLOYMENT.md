# Vercel Deployment Guide

## Required Environment Variables

Add these environment variables in your Vercel project settings:

### Frontend (Next.js) Environment Variables

1. **NEXT_PUBLIC_API_URL** (Required)
   - Your backend API URL
   - Example: `https://your-backend.vercel.app/api` or `https://api.yourdomain.com/api`
   - If your backend is on a different platform, use that URL
   - **Important**: Include `/api` at the end if your backend routes start with `/api`

### Setting Environment Variables in Vercel

1. Go to your Vercel project dashboard
2. Navigate to **Settings** → **Environment Variables**
3. Add `NEXT_PUBLIC_API_URL` with your backend URL
4. Make sure to set it for **Production**, **Preview**, and **Development** environments
5. Redeploy your application

## Common Issues and Solutions

### Serverless Function Crashes

If you're experiencing serverless function crashes:

1. **Check Environment Variables**: Ensure `NEXT_PUBLIC_API_URL` is set correctly in Vercel
2. **Check Backend URL**: Make sure your backend is accessible and the URL is correct
3. **CORS Configuration**: Ensure your backend has CORS configured to allow requests from your Vercel domain

### Image Loading Issues

- The Next.js config now supports remote images from any domain
- Make sure your backend image URLs are accessible publicly
- If using HTTPS for backend, ensure SSL certificates are valid

## Backend Deployment

If deploying backend to Vercel:

1. Ensure your backend supports serverless functions
2. Configure CORS to allow your frontend domain
3. Set up MongoDB or your database connection string in backend environment variables

## Quick Checklist Before Deploying

- [ ] `NEXT_PUBLIC_API_URL` is set in Vercel environment variables
- [ ] Backend is deployed and accessible
- [ ] CORS is configured on backend for your Vercel domain
- [ ] Database connection is configured
- [ ] Image uploads are working (if applicable)
