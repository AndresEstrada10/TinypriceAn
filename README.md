# TinyPrice

Práctica Android de Andrés Estrada basada en https://epanchanaf.github.io/tinyprice-codelab/.
Las fuentes iniciales proceden de la referencia pública del codelab de epanchanaf.

## Ejecutar

Android Studio, JDK 17 o superior, SDK 37 y Gradle 9.6 (wrapper incluido).
`local.properties` debe indicar la ubicación local del Android SDK.

```powershell
.\gradlew.bat :app:testDebugUnitTest :app:assembleDebug
```

Por defecto consulta el proyecto `tinyprice` de Andrés en Supabase. Para usar datos de demostración sin red:

```powershell
.\gradlew.bat :app:assembleDebug -PuseRemoteDeals=false
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

- Proyecto `cruunmqluwtuqcfbfjqa` creado en la organización ADS y función `search-products` desplegada.
- Endpoint verificado: consulta vacía devuelve HTTP 400; sin el secreto TinyFish devuelve HTTP 503 con `TINYFISH_NOT_CONFIGURED`.
- Búsqueda real verificada el 24 de octubre de 2026: `Nintendo Switch OLED Ecuador` devuelve HTTP 200 y 8 resultados, con enlaces de fuentes reales.
- Pendiente probar el recorrido Android en celular.
- Compilación `assembleDebug` y 3 pruebas unitarias del ViewModel correctas (24 de octubre de 2026).
