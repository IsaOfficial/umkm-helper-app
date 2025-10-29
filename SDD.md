# Software Design Document (SDD) — UMKM Helper (MVP)

## 1. Overview Arsitektur
- **Client:** Flutter (Dart)
- **Backend:** Firebase (Authentication, Firestore, Cloud Functions - optional) OR simple REST API (Node.js/Express) jika diinginkan.
- **Local DB:** Hive atau SQLite untuk cache/offline.
- **Storage:** Firebase Storage untuk foto produk.

Arsitektur: Mobile (Flutter) -> Local DB (Hive) + Remote (Firestore). Sync strategy: offline-first with background sync.

## 2. Teknologi & Dependensi
- Flutter 3.x atau 4.x
- Packages: firebase_auth, cloud_firestore, firebase_storage, provider / riverpod, hive, flutter_local_notifications, image_picker, csv
- Dev tools: Dart analyzer, Flutter DevTools.

## 3. Modul & Komponen
1. **Auth Module**
   - Fungsi: register, login, logout, profile update.
   - API: Firebase Auth.

2. **Shop Module**
   - Fungsi: shop profile CRUD.

3. **Product Module**
   - Fungsi: CRUD produk, upload gambar (Firebase Storage), local cache.
   - Data model: Product (id, shop_id, name, desc, price, stock, image_url, created_at)

4. **Order Module**
   - Fungsi: create order, update status, calculate totals, decrement stock.
   - Status flow: NEW -> PROCESSING -> SHIPPED -> COMPLETED -> CANCELLED

5. **Reporting Module**
   - Fungsi: aggregate transactions per day/month, export CSV.

6. **Sync Module**
   - Fungsi: sync local db <-> firestore, resolve conflicts (last-write-wins for MVP).

## 4. Data Flow
- User updates product -> write to local DB -> enqueue sync job -> push to Firestore -> upload image to Storage -> confirm sync.

## 5. API Contracts (if using REST)
- `POST /api/v1/auth/register` {name, email, password} -> 201 {user}
- `POST /api/v1/auth/login` {email, password} -> 200 {token, user}
- `GET /api/v1/shops/{shopId}/products` -> 200 [{product}]
- `POST /api/v1/shops/{shopId}/products` {product data} -> 201 {product}
- `GET /api/v1/shops/{shopId}/orders` -> 200 [{order}]
- `POST /api/v1/shops/{shopId}/orders` {order data} -> 201 {order}

## 6. UI Wireframes (Deskripsi)
- Splash & Auth screens
- Dashboard (cards: today revenue, new orders)
- Product List (grid), Product Detail, Product Form
- Orders List, Order Detail (ubah status)
- Reports page (date picker, export CSV)

## 7. Security Considerations
- Use Firebase rules to restrict read/write to owner only.
- Validate image file types & sizes client-side.

## 8. Deployment Notes
- Setup Firebase project, enable Auth (Email, Google), create Firestore rules, setup Storage bucket.
- For production, enable app signing and store keys securely.

