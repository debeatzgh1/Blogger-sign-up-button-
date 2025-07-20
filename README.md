# 📨 Blogger Floating Subscribe Popup (with Firebase or EmailJS)

This project provides a **floating subscribe button** for Blogger that triggers a **pop-up email signup form**. Designed to be fully compatible with Blogger and easily pasteable into any post or page in HTML view.

> 📌 Perfect for bloggers, creators, and marketers who want to grow their email list using a sleek, mobile-friendly form.

---

## ✨ Features

- 💬 Floating “Subscribe” button
- 💌 Pop-up email form with Name & Email fields
- ✅ Email auto-responder via [EmailJS](https://www.emailjs.com)
- ✅ Firebase-ready if needed
- 📱 Responsive design (mobile-friendly)
- 🧩 Fully works in Blogger (no external hosting required)

---

## 📦 Installation

### Option 1: Use in Blogger

1. Go to your Blogger dashboard.
2. Create a **new Page** or **Post**.
3. Click **HTML** view.
4. Paste the contents of `index.html`.
5. Replace the following placeholders:

```js
emailjs.init("YOUR_USER_ID");
emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", { name, email });
