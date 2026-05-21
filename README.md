# Patagonia Showroom — Rental · Descargas

Este repositorio contiene los APKs públicos de la app **Patagonia Showroom - Rental** (Android).

- Página de descarga: **https://kyojinlabs.github.io/rental-app-downloads/**
- App principal (privado): [`kyojinlabs/rental-app`](https://github.com/kyojinlabs/rental-app)

## Cómo se publica una nueva versión

Las nuevas versiones se publican desde el repo principal (`rental-app`) corriendo:

```bash
npm run fastlane:android:publish
```

Ese lane:

1. Compila el APK firmado de release.
2. Crea un GitHub Release con tag `v{version}` y adjunta `rentalapp-v{version}.apk`.
3. Actualiza `latest.json` en este repo.
4. GitHub Pages publica los cambios en pocos segundos.

## Estructura del repo

```
.
├── .nojekyll          # desactiva Jekyll (servimos archivos crudos)
├── README.md          # este archivo
├── index.html         # página de descarga (HTML/CSS/JS plano)
├── latest.json        # manifiesto de la versión actual (lo actualiza Fastlane)
└── assets/
    └── logo.png       # logo de la app
```

## `latest.json` — esquema

```json
{
  "version": "1.0.0",
  "versionCode": null,
  "apkUrl": "https://github.com/kyojinlabs/rental-app-downloads/releases/download/v1.0.0/rentalapp-v1.0.0.apk",
  "apkSize": 0,
  "sha256": "<sha256 hex>",
  "releasedAt": "2026-05-21T17:30:00Z",
  "releaseNotes": "...",
  "minAndroidVersion": "7.0"
}
```

## Instalación en Android

1. Abrí la página de descarga desde el dispositivo.
2. Tocá **Descargar APK**.
3. Habilitá *Instalar apps de fuentes desconocidas* para tu navegador (Ajustes → Apps → Acceso especial → Instalar apps desconocidas).
4. Abrí el archivo descargado y seguí los pasos del instalador.

La app está firmada con el keystore privado del equipo. No está distribuida vía Play Store.
