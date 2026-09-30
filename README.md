# La Embajada de Cristo — App de administración (APK)

App Android (Capacitor + Firebase) con: finanzas (ingresos, egresos, gastos generales y mayores),
presupuesto de la obra, inventario, fotos de facturas, informes en Excel y copia de seguridad para Drive.
Dos roles: **administrador** (todo) y **técnico** (solo gastos mayores de la obra e inventario).

## 1. Crear la nube (Firebase, gratis para empezar)
1. Entra a https://console.firebase.google.com y crea un proyecto.
2. **Authentication** > Comenzar > activa **Correo y contraseña**. En "Usuarios" crea dos: el administrador y el técnico.
3. **Firestore Database** > Crear base de datos. En "Reglas" pega el contenido de `firestore.rules` y publica.
4. **Storage** > Comenzar. En "Reglas" pega `storage.rules` y publica.
5. En Firestore crea la colección `usuarios`. Un documento por persona: el ID del documento es el **UID** del usuario y tiene un campo `rol` con el texto `admin` o `tecnico`.
6. **Configuración del proyecto** > Tus apps > agrega una app **Web** y configura los valores `VITE_FIREBASE_*`.

## 2. Generar el APK
Actions > "Generar APK" > Run workflow. El artefacto resultante se llama **LaEmbajadaDeCristo-APK** y contiene `app-debug.apk`.
