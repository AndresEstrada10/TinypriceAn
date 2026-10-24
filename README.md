# TinyPrice

Práctica Android de Andrés Estrada basada en https://epanchanaf.github.io/tinyprice-codelab/.
Las fuentes iniciales proceden de la referencia pública del codelab de epanchanaf.

## Ejecutar

Android Studio, JDK 17 o superior, SDK 37 y Gradle 9.6 (wrapper incluido).
`local.properties` debe indicar la ubicación local del Android SDK.

```powershell
.\gradlew.bat :app:testDebugUnitTest :app:assembleDebug
```

Por defecto funciona con datos de demostración. Para conectar el proyecto propio de Supabase:

```powershell
.\gradlew.bat :app:assembleDebug -PuseRemoteDeals=true -PedgeRuntimeBaseUrl=https://PROJECT_REF.supabase.co/functions/v1
```

El teléfono debe tener Android 6.0 o posterior. Con un dispositivo autorizado:

```powershell
.\gradlew.bat :app:connectedDebugAndroidTest
```

## Backend

La función está en `supabase/functions/search-products/index.ts`.
Guardar `TINYFISH_API_KEY` exclusivamente como secreto de Supabase.
No incluir claves, credenciales, APK ni archivos locales en Git.
La función pública es didáctica; requiere autenticación y límites compartidos antes de distribuirse públicamente.

## Estado de verificación

- Pendiente confirmar la conexión de Supabase de Andrés.
- Pendiente probar búsqueda real y recorrido en celular.
- Compilación `assembleDebug` y 3 pruebas unitarias del ViewModel correctas (24 de octubre de 2026).
