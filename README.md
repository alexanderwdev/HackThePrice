# HackThePrice

**Agregador automático de ofertas tecnológicas** para las principales tiendas españolas.

> Proyecto personal desarrollado como parte de mi formación en FP Superior de DAM.

---

## ¿Qué es?

HackThePrice monitoriza cada hora las webs de PcComponentes, MediaMarkt, Carrefour, GAME, Coolmod y Worten en busca de productos con descuento real (precio tachado vs. precio actual). Los resultados se publican automáticamente en esta landing page.

**Demo en vivo:** https://alexanderwdev.github.io/HackThePrice/

---

## Funcionalidades

- Filtro por tienda, precio máximo y porcentaje de descuento mínimo
- Buscador de productos en tiempo real
- Ordenación por mayor descuento, mayor ahorro o menor precio
- Paginación del catálogo (12 productos por página)
- Actualización automática cada hora sin intervención manual

---

## Stack tecnológico

| Capa | Tecnología |
|---|---|
| Frontend | HTML5, CSS3, JavaScript (Vanilla) |
| Hosting | GitHub Pages |
| CI/CD | GitHub Actions |
| Datos | JSON estático regenerado automáticamente |

La página es 100% estática: no necesita servidor. Toda la lógica de filtrado, búsqueda, ordenación y paginación corre en el cliente con JavaScript puro.

---

## Arquitectura

```
Pipeline backend (automatizado)
        │
        ▼
  Scraping horario
  de 6 tiendas ES
        │
        ▼
  Detección de ofertas
  (solo descuentos reales
   con precio tachado)
        │
        ▼
  deals.json ──► GitHub Pages
                      │
                      ▼
               Landing page
               (este repo)
```

El backend es un pipeline Python que se ejecuta automáticamente cada hora con GitHub Actions. Genera un `deals.json` que esta página consume directamente desde el cliente.

---

## Lo que he practicado

- **JavaScript sin frameworks**: manipulación del DOM, eventos, filtros en tiempo real, paginación
- **CSS moderno**: variables CSS, diseño responsive, transiciones, grid layout
- **GitHub Actions**: automatización de CI/CD y publicación en GitHub Pages mediante la API REST de GitHub
- **Arquitectura JAMstack**: separación entre pipeline de datos y capa de presentación
- **Web scraping ético**: extracción de datos públicos respetando tiempos de espera

---

## Autor

**Alexander W.** — Estudiante de FP Superior de DAM  
[GitHub](https://github.com/alexanderwdev)
