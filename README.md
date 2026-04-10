# 🌍 Temporada Mundial

Globo interactivo que muestra qué frutas y verduras están en temporada en cada país del mundo, mes a mes.

**[Ver en vivo →](https://temporadamundial.com)**

## Stack
- Globe.gl (Three.js) para el globo 3D con choropleth
- HTML/CSS/JS puro — zero build step
- Datos basados en FAO y ministerios agrícolas nacionales
- Deploy automático en Vercel

## Estructura
```
├── index.html          # Globo interactivo principal
├── data/
│   └── seasonal.json   # Datos de temporada (~140 países)
├── pages/              # Páginas SEO por país/mes
└── assets/
```

## Datos
`data/seasonal.json` usa códigos ISO 3166-1 alpha-3. Cada país tiene:
- `name`: nombre en español
- `items`: array de productos con tipo (`fruta`/`verdura`) y meses de temporada (0=Enero)

## Desarrollo local
Necesitas un servidor local porque el `index.html` hace `fetch()` al JSON.

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Luego abre `http://localhost:8000`

## Contribuir
Los datos de temporada son aproximados — si ves algo incorrecto para tu región, abre un PR.
