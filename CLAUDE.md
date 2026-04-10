# Temporada Mundial — Contexto del Proyecto

## Qué es esto
Web interactiva con un globo 3D tipo Google Earth que muestra qué frutas y verduras están en temporada en cada país del mundo, mes a mes. El objetivo es posicionarla en SEO y monetizarla con afiliados y newsletter.

## Stack actual
- **Frontend**: HTML/CSS/JS puro — un solo `index.html` por ahora
- **Globo**: Globe.gl (Three.js) con polígonos choropleth por país
- **Datos**: Embebidos en `data/seasonal.json` — ~140 países con productos por mes
- **Hosting**: Vercel (deploy automático desde GitHub)
- **Dominio**: temporadamundial.com (o pendiente de definir)

## Estructura del proyecto
```
temporada-mundial/
├── index.html          ← globo interactivo principal
├── data/
│   └── seasonal.json   ← datos de temporada (fuente: FAO, ministerios agrícolas)
├── pages/              ← páginas SEO estáticas por país/mes (a construir)
├── assets/
│   └── og-image.png    ← imagen para Open Graph (a crear)
├── CLAUDE.md           ← este archivo
├── README.md
└── .gitignore
```

## Formato de datos (seasonal.json)
```json
{
  "ESP": {
    "name": "España",
    "name_en": "Spain",
    "items": [
      { "n": "Fresas", "t": "fruta", "m": [2, 3, 4, 5] },
      { "n": "Tomates", "t": "verdura", "m": [5, 6, 7, 8, 9] }
    ]
  }
}
```
- Claves: ISO 3166-1 alpha-3
- `m`: array de meses (0=Enero ... 11=Diciembre)
- `t`: "fruta" o "verdura"

## Prioridades actuales
1. Separar datos del HTML → `data/seasonal.json`
2. Hacer que el globo cargue los datos desde el JSON
3. Subir a GitHub y conectar a Vercel
4. Crear páginas SEO individuales: `/frutas-temporada-espana-enero`, etc.
5. Agregar newsletter (Mailchimp o Resend)

## Monetización planeada
- Afiliados: Amazon Fresh, Mercadona, Carrefour (links por producto)
- Newsletter mensual de temporada
- API de datos (futuro)

## Idioma
El sitio es en español. El código puede estar en inglés. Commits en inglés.

## Notas técnicas
- El globo usa `world-atlas@2` con TopoJSON para los polígonos
- Los colores van de verde claro (1-2 productos) a verde oscuro (5+)
- Fondo oscuro tipo "night mode" para que resalte el globo
- No usar frameworks por ahora — mantener simple y rápido
