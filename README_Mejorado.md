# La Embajada de Cristo — versión mejorada

## Configuración Firebase
Configure como Secrets de GitHub los seis valores de la configuración Web de Firebase:

- `VITE_FIREBASE_API_KEY`
- `VITE_FIREBASE_AUTH_DOMAIN`
- `VITE_FIREBASE_PROJECT_ID`
- `VITE_FIREBASE_STORAGE_BUCKET`
- `VITE_FIREBASE_MESSAGING_SENDER_ID`
- `VITE_FIREBASE_APP_ID`

En Firebase:
1. Active Authentication > Correo/contraseña.
2. Cree los usuarios administrador y técnico.
3. En Firestore cree `usuarios/{UID}` con `rol: "admin"` o `rol: "tecnico"`.
4. Publique `firestore.rules`.
5. Publique `storage.rules`.

## Desarrollo
```bash
npm install
npm run dev
```

## APK con GitHub Actions
Actions > Generar APK > Run workflow.
El artefacto resultante se llama `LaEmbajadaDeCristo-APK` y contiene `app-debug.apk`.

## Permisos
- Administrador: finanzas completas, presupuesto, inventario, exportaciones, respaldo/restauración y eliminaciones.
- Técnico: únicamente gastos mayores permitidos por reglas e inventario.
