# NABASKI
 
A website for a photography business, with a booking system, password-protected client galleries and a print shop. The frontend is built in **React** and talks to two **Express** servers: one for bookings and portfolio images stored in **SQLite**, and one for client galleries, likes and comments.
 
---
 
## Features
 
**Portfolio**
- Galleries by category (weddings, family, children, models)
- Image carousel and full-size image modal
- Image search across the portfolio
- Prices page and testimonials
**Booking and contact**
- Book a meeting or consultation with a date and time picker
- Bookings are saved to the database
- Contact form that sends email through EmailJS
**Client galleries**
- Each client gets a private gallery opened with a password
- Like and comment on images
- Order prints in different sizes from the gallery
**Shop**
- Cart and checkout for prints
**Admin**
- Create, edit and delete client galleries with cover image and password
- Upload portfolio images by category, with client-side compression
- Delete images and moderate comments
- View incoming bookings
---
 
## Tech Stack
 
| Layer | Technology |
|---|---|
| Frontend | React 18, Vite, React Router, React Datepicker, Font Awesome |
| Backend | Node.js, Express (two servers) |
| Database | SQLite (bookings, portfolio images), JSON files (galleries, comments) |
| File uploads | Multer, browser-image-compression |
| Email | EmailJS |
| Dates | date-fns, date-fns-tz |
 
---
 
## Architecture
 
```
nabaski/
├── server/
│   ├── server.js           # Bookings and portfolio API (SQLite)
│   ├── nabaski.sql         # Database schema
│   └── uploads/portfolio/  # Uploaded portfolio images
├── galleryServer.js        # Client galleries, likes and comments API
├── galleries.json          # Gallery data
├── comments.json           # Likes and comments per image
└── src/                    # React + Vite client
    ├── pages/              # Start page, portfolio categories, booking, client galleries, admin …
    └── components/         # Header, footer, carousel, image modal, testimonials …
```
 
The project is split into two APIs with different responsibilities. Bookings and portfolio images live in a relational SQLite database, while client galleries, likes and comments are stored as JSON on the gallery server. Images are compressed in the browser before upload to keep file sizes and upload times down.
 
**Nathalie Kanfjäll Baskin**
[Portfolio](https://www.nathaliebaskin.com) · [LinkedIn](https://www.linkedin.com/in/nathalie-baskin-b61790193) · [GitHub](https://github.com/Namahka)
