[FIREBASE_SETUP.md](https://github.com/user-attachments/files/27552341/FIREBASE_SETUP.md)
# Koppla Petlio till Firebase

## 1. Skapa projekt
1. Gå till Firebase Console.
2. Skapa ett projekt för Petlio.
3. Lägg till en Web App.
4. Kopiera `firebaseConfig`.

## 2. Klistra in config i `index.html`
Sök efter:

```js
window.PETLIO_FIREBASE_CONFIG = {
  apiKey: "",
  authDomain: "",
  projectId: "",
  storageBucket: "",
  messagingSenderId: "",
  appId: ""
};
```

Byt de tomma värdena mot värdena från Firebase.

## 3. Aktivera Authentication
Firebase Console -> Authentication -> Sign-in method.
Aktivera Email/Password.

## 4. Skapa Firestore
Firebase Console -> Firestore Database.
Skapa databasen i production mode.

## 5. Lägg in regler
Kopiera innehållet från `firestore.rules` till Firestore Rules och publicera.

## 6. Vad appen sparar nu
När configen är ifylld sparas:
- Profiler i `profiles`
- Annonser i `listings`
- Användarens e-post i `users`

Lösenord sparas inte i Firestore. Firebase Authentication hanterar lösenord säkert.

## Nästa steg
För riktig lansering behöver vi lägga till Firebase Storage för uppladdade bilder, eftersom stora bilder inte ska ligga direkt i Firestore.
