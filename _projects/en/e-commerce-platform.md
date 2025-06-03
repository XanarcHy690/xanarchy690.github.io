---
# BENZERSİZ PROJE KİMLİĞİ: 
# Bu ID, projenin farklı dillerdeki versiyonlarını birbirine bağlar.
# Her iki dildeki .md dosyasında da AYNI olmalıdır.
# Küçük harf, rakam ve tire (-) kullanın. Boşluk veya özel karakter kullanmaktan kaçının.
id: e-commerce-platform 

# SIRALAMA:
# Projelerin ana sayfada hangi sırada görüneceğini belirler (isteğe bağlı).
# Küçük sayılar daha önce gelir.
order: 1

# BAŞLIK (Dil Spesifik):
# Projenin bu dildeki başlığı. Modal penceresinde ve proje kartında görünür.
title: "E-Commerce Platform"

# KISA AÇIKLAMA (Dil Spesifik):
# Proje kartında görünecek kısa, bir veya iki cümlelik özet.
short_description: "A full-featured online shopping platform developed with modern React and Node.js technologies, offering a seamless user experience."

# ETİKETLER (Dil Spesifik olabilir veya ortak tutulabilir):
# Projede kullanılan ana teknolojiler veya anahtar kelimeler. 
# Proje kartında ve modalda gösterilebilir.
tags: ["React", "Node.js", "MongoDB", "TypeScript", "Express.js", "Stripe"]

# PROJE KARTI GÖRSEL AYARLARI (Kapak resmi yoksa kullanılır):
image_gradient_from: "ctp-blue"   # Renk geçişinin başlangıç rengi (Tailwind renk sınıfı)
image_gradient_to: "ctp-sapphire" # Renk geçişinin bitiş rengi

# PROJE KARTI İKONU:
# Kapak resmi yoksa veya kapak resminin üzerinde küçük bir ikon olarak gösterilir.
# Font Awesome sınıfını kullanın.
icon_class: "fas fa-shopping-cart"

# KAPAK GÖRSELİ (İsteğe Bağlı):
# Proje kartında gösterilecek ana görsel. Eğer bu alan varsa, image_gradient_* alanları kullanılmaz.
# Yol, projenizin kök dizinine göre olmalı ve başında / olmalı.
cover_image: "/assets/images/projects/ecommerce-cover.jpg" 

# LİNKLER:
github_url: "https://github.com/yourusername/ecommerce-project" # Projenin GitHub deposu (varsa)
# live_url: "https://your-ecommerce-demo.com" # Projenin canlı demo adresi (varsa)
---

## About The Project

This is where you provide a **detailed description** of your project in English. You can use standard Markdown formatting here.

Our e-commerce platform was designed to provide a seamless and modern online shopping experience. Key goals included a user-friendly interface, robust backend capabilities, and secure transaction processing. We focused on scalability to accommodate growing product catalogs and user bases.

![Main Page Screenshot]({{ '/assets/images/projects/ecommerce-cover.jpg' | relative_url }})
*<center><small>Fig. 1: The main landing page showcasing featured products.</small></center>*

The platform allows users to:
- Browse product categories and individual items.
- View detailed product information, including images, descriptions, and reviews.
- Add products to a shopping cart and manage cart contents.
- Proceed through a secure multi-step checkout process.
- Manage their user account, order history, and saved addresses.

### Features

*   **Responsive Design:** Fully accessible on desktops, tablets, and mobile devices.
*   **User Authentication:** Secure registration and login functionality.
*   **Product Management:** Admin interface for adding, editing, and removing products.
*   **Search & Filtering:** Advanced search capabilities with filters for price, category, etc.
*   **Shopping Cart & Checkout:** Intuitive cart management and integration with Stripe for payments.
*   **Order Management:** Users can view their order history; admins can manage orders.
*   **Wishlist Functionality:** Users can save products for later.

![Admin Dashboard Screenshot]({{ '/assets/images/projects/ecommerce-cover.jpg' | relative_url }})
*<center><small>Fig. 2: Admin dashboard for managing site statistics and orders.</small></center>*

### Technical Details

The project was built using the MERN stack with some variations:

*   **Frontend:** React.js with Vite, TypeScript, Tailwind CSS for styling, and Redux Toolkit for state management.
*   **Backend:** Node.js with Express.js framework, implementing a RESTful API.
*   **Database:** MongoDB Atlas (cloud-hosted) for product, user, and order data.
*   **Authentication:** JWT (JSON Web Tokens) for secure API access.
*   **Payment Integration:** Stripe API for processing credit card payments.
*   **Deployment:** Frontend على Vercel, Backend على Render (veya Heroku).

This project demonstrates proficiency in full-stack web development, API design, and e-commerce best practices.