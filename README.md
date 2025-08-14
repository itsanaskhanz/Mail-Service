# Mail Service

A modern serverless mail service built with Node.js and Nodemailer, designed for seamless email delivery from your frontend forms. Effortlessly handle contact requests, feedback, or notifications with proper CORS handling. Fully deployable on Vercel for fast setup, smooth development, and scalable serverless execution.

## Technologies Used

- Node.js
- Nodemailer
- Vercel

## Setup Guide

### Clone the Repository

1. Clone the repository:

```bash
git clone <repository_url>
cd <repository_folder>
```

### Mail Service Setup

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file in the backend root directory with the following:

```env
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=465
EMAIL_USER=author-email-here
EMAIL_PASS=author-email-app-password
EMAIL_TO=author-email-here
FRONTEND_URL=frontend-url-here
```

3. Start Mail Service Locally:

```bash
npm run local
```

### Deploy to Vercel

1. Install Vercel CLI (if not already installed):

```bash
npm i -g vercel
```

2. Login to Vercel:

```bash
vercel login
```

3. Deploy the project:

```bash
vercel --prod
```

4. Set environment variables in **Vercel Dashboard → Project → Settings → Environment Variables**:

```env
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=465
EMAIL_USER=author-email-here
EMAIL_PASS=author-email-app-password
EMAIL_TO=author-email-here
FRONTEND_URL=frontend-url-here
```

### Test the deployed serverless API using `curl`:

```bash
curl -X POST https://your-vercel-project.vercel.app/api/send-mail \
-H "Content-Type: application/json" \
-d '{
  "name": "Anas",
  "email": "visitor@example.com",
  "company": "My Company",
  "message": "Hello, testing the mail-service!"
}'
```

Expected Response:

```json
{
  "success": true,
  "message": "Email sent successfully!"
}
```

### Notes

- FRONTEND_URL must match your frontend origin to avoid CORS errors.  
- Gmail requires **2FA + App Password** for serverless SMTP.  
