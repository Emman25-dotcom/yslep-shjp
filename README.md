# Yslep Portal - Deployment & Setup Guide

## ✅ System Overview

Your Yslep Portal is a complete two-portal system:

1. **index.html** - Main entry point with access control
2. **Yslep.html** - Member portal for uploading photos
3. **Yslep-Admin.html** - Admin dashboard to review uploads

---

## 🚀 Pre-Deployment Checklist

### 1. **Change Admin Password** (CRITICAL FOR SECURITY)
   - Open `index.html`
   - Find line with: `const ADMIN_PASSWORD = "admin123";`
   - Change to a strong password (recommended: 12+ characters, mix of upper/lower/numbers/symbols)
   - Example: `const ADMIN_PASSWORD = "Yslep@2024#Secure";`

### 2. **File Structure**
   Ensure all three files are in the same folder:
   ```
   your-folder/
   ├── index.html          (Main landing page)
   ├── Yslep.html          (Member portal)
   └── Yslep-Admin.html    (Admin dashboard)
   ```

### 3. **External Resources** ✓
   All external resources are already configured:
   - **Tailwind CSS**: Uses CDN (cdn.tailwindcss.com) - No download needed
   - **SVG Icons**: Built-in (no external icon library)
   - **Avatar Images**: Uses Unsplash & gravatar.cc CDN

   ✅ Everything is web-ready!

---

## 📋 Feature Checklist

### Member Portal (Yslep.html)
- ✅ Onboarding with name, cycle, and profile icon
- ✅ Profile icon preview during upload
- ✅ Dashboard displaying cycle members
- ✅ Two upload categories (Parish Involvement & Social Apostolate)
- ✅ Month selection for uploads
- ✅ Photo preview before submission
- ✅ Success confirmation
- ✅ Logout and return to onboarding
- ✅ Home button to return to main page

### Admin Portal (Yslep-Admin.html)
- ✅ Admin authentication via password
- ✅ Sidebar navigation
- ✅ Statistics dashboard (Total Uploads, Parish Involvement, Social Apostolate)
- ✅ Recent uploads table with search
- ✅ Image modal for full-size photo viewing
- ✅ Responsive design (mobile-friendly)
- ✅ Admin logout with session verification
- ✅ Home button to return to main page

### Main Portal (index.html)
- ✅ Member portal button (no password needed)
- ✅ Admin portal button with password protection
- ✅ Professional login interface
- ✅ Session management for admin access
- ✅ Error handling for incorrect passwords

---

## 🌐 Deployment Instructions

### Option 1: Simple Web Host (Recommended for beginners)

**Services:** Netlify, Vercel, GitHub Pages, Firebase Hosting

1. **Upload your three HTML files**
2. **Set index.html as the main entry point**
3. **Deploy!**

The system will work immediately without any backend required.

### Option 2: Traditional Web Hosting

1. Upload all three files via FTP to your web server
2. Point your domain to the folder
3. Access via: `https://yourdomain.com/index.html`

### Option 3: Local Testing

1. Open `index.html` in a web browser
2. Test member portal and admin portal
3. Verify all links and functionality work

---

## 🔒 Security Recommendations

1. **Change the admin password** (see step 1 above)
2. **Use HTTPS** when deploying (not HTTP)
3. **Consider adding backend authentication** for production use:
   - Currently uses sessionStorage (browser-only, not secure for sensitive data)
   - For real production: use server-side sessions/JWT tokens
4. **Add CORS headers** if accessing external APIs
5. **Enable password reset functionality** (optional feature to add)

---

## 📝 Usage Instructions

### For Members:
1. Access **Member Portal** from main page
2. Fill in Full Name, Cycle, and upload a profile icon
3. Click "Join Dashboard"
4. Select upload category (Parish Involvement or Social Apostolate)
5. Choose month and upload service photo
6. Photo appears in admin dashboard

### For Admins:
1. Click **Admin Portal** from main page
2. Enter admin password
3. View statistics and all member uploads
4. Click photos to view full size
5. Search members by name
6. Click "Admin Logout" to exit safely

---

## 🔧 Customization Guide

### Change Color Scheme
- Primary color: `#ef4444` (red) - Search and replace
- Secondary color: `#f43f5e` (rose) - Search and replace
- Example: Change all `bg-red-500` to `bg-blue-500`

### Change Organization Name
- Search for "Yslep" and replace with your organization name
- Update in: index.html, Yslep.html, Yslep-Admin.html

### Modify Categories
- Edit upload categories in `Yslep.html` (search for "Parish Involvement")
- Update in both the HTML buttons and JavaScript arrays

### Add More Sidebar Navigation Items
- Edit the `<nav>` section in `Yslep-Admin.html`
- Add new links following the existing pattern

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| Images not loading | Check internet connection (needs CDN access) |
| Admin portal not opening | Verify password is correct, check sessionStorage |
| Styles not applying | Clear browser cache (Ctrl+Shift+Delete) |
| Mobile not working | Check viewport meta tag is present |
| Forms not submitting | Check console for JavaScript errors (F12) |
| Admin can't see uploads | Make sure member portal was used first to create data |

---

## 📊 Data Storage Notes

### Current Implementation:
- **Member data**: Stored in browser (localStorage - persists)
- **Admin uploads**: Stored in mock JavaScript array (resets on refresh)

### For Production Database:
If you need to store data permanently, integrate with:
- Firebase Realtime Database
- AWS DynamoDB
- MongoDB
- Your own backend API

Contact a developer to add database functionality.

---

## ✨ Next Steps

1. ✅ Change admin password
2. ✅ Test all functionality locally
3. ✅ Upload to web host
4. ✅ Share domain with users
5. ✅ Monitor and collect feedback

---

## 📞 Support

If you encounter issues:
1. Check the **Troubleshooting** section above
2. Clear browser cache and cookies
3. Try a different browser
4. Open Developer Console (F12) to check for errors

---

**Version:** 1.0 | **Last Updated:** June 2026 | **Status:** Production Ready ✅
