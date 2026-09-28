# Aastha Digital Store v4 — Product Only

Firebase-backed Android app for selling physical products only. **No Firebase Cloud Storage is used**, so product files/PDF downloads are not part of this version.

## Features
- Firebase Email/Password admin login
- Firestore product catalog
- Add physical products with name, price and description
- UPI payment intent
- Orders stored in Firestore with pending status
- UPI ID can be changed from Admin

## Firebase setup
1. Create/open the Firebase project.
2. Android package: `com.aastha.digitalstore`.
3. Keep the supplied `google-services.json` in `app/google-services.json`.
4. Enable Authentication > Email/Password.
5. Create Firestore Database.
6. **Do not enable Firebase Storage for this version.**
7. Create the admin user in Firebase Authentication.

## Firestore
`settings/store`: `{ upiId: "motog2025my@oksbi" }`

`products/{id}`: `name`, `price`, `description`, `active`

`orders/{id}`: `productId`, `productName`, `amount`, `status`, `createdAt`, `buyerUid`

## Payment note
A static UPI ID/UPI intent does not by itself verify that money was received. The app currently creates a `pending` order after the customer taps “PAYMENT DONE”. Automatic payment confirmation would require a payment gateway and server-side/webhook verification.
