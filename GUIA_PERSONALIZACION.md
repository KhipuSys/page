# Guía de Personalización - RoboTech

## 🎨 Cómo Personalizar tu Página Web

### 1. Cambiar el Nombre de la Empresa

En `index.html`, busca y reemplaza "RoboTech" por el nombre de tu empresa:

```html
<!-- Línea 19 - Logo -->
<div class="nav__logo">
    <a href="#home">TU_EMPRESA</a>
</div>

<!-- Línea 8 - Título de la página -->
<title>TU_EMPRESA - Proyectores de Robótica</title>
```

### 2. Agregar Imágenes del Producto

#### Para la sección Hero:
Reemplaza el div placeholder (línea ~65) con una imagen real:

```html
<!-- Antes -->
<div class="hero__placeholder">
    <span>Imagen del Producto</span>
</div>

<!-- Después -->
<img src="assets/images/hero-producto.jpg" alt="Proyector de Robótica" class="hero__image-img">
```

Y en `assets/css/components.css`, agrega:

```css
.hero__image-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: var(--border-radius-lg);
}
```

#### Para los productos:
Reemplaza los placeholders en las tarjetas de productos (línea ~85):

```html
<!-- Antes -->
<div class="product-card__placeholder">
    <span>Producto 1</span>
</div>

<!-- Después -->
<img src="assets/images/producto-1.jpg" alt="Proyector RoboTech Pro" class="product-card__img">
```

#### Para la galería:
Similar a los productos, reemplaza los placeholders (línea ~175):

```html
<img src="assets/images/galeria-1.jpg" alt="Galería 1" class="gallery__img">
```

### 3. Cambiar Colores

En `assets/css/main.css`, modifica las variables CSS (líneas 4-15):

```css
:root {
    --color-primary: #0071e3;        /* Color principal (azul Apple) */
    --color-primary-dark: #0077ed;   /* Color principal oscuro */
    --color-secondary: #86868b;      /* Color secundario */
    --color-text: #1d1d1f;           /* Color del texto */
    --color-background: #ffffff;     /* Color de fondo */
}
```

### 4. Modificar Información de Contacto

En `index.html`, busca la sección de contacto (línea ~195) y actualiza:

```html
<div class="contact__item">
    <h3 class="contact__item-title">Email</h3>
    <p class="contact__item-text">tu-email@ejemplo.com</p>
</div>
<div class="contact__item">
    <h3 class="contact__item-title">Teléfono</h3>
    <p class="contact__item-text">+1 (555) 123-4567</p>
</div>
```

### 5. Actualizar Redes Sociales

Reemplaza los enlaces de redes sociales (línea ~205):

```html
<div class="contact__social">
    <a href="https://facebook.com/tuempresa" class="contact__social-link">Facebook</a>
    <a href="https://twitter.com/tuempresa" class="contact__social-link">Twitter</a>
    <a href="https://instagram.com/tuempresa" class="contact__social-link">Instagram</a>
</div>
```

### 6. Modificar Productos

Para agregar, eliminar o modificar productos, edita la sección de productos (línea ~75):

```html
<article class="product-card">
    <div class="product-card__image">
        <img src="assets/images/producto.jpg" alt="Nombre del Producto">
    </div>
    <div class="product-card__content">
        <h3 class="product-card__title">Nombre del Producto</h3>
        <p class="product-card__description">Descripción del producto</p>
        <div class="product-card__price">$299.99</div>
        <a href="#contacto" class="btn btn--primary btn--small">Comprar</a>
    </div>
</article>
```

### 7. Configurar el Formulario de Contacto

El formulario actualmente muestra una alerta. Para conectarlo a un servicio real:

1. **Usar un servicio de formularios** (Formspree, Netlify Forms, etc.)
2. **Crear un backend** (Node.js, Python, PHP, etc.)
3. **Modificar `assets/js/main.js`** (línea ~40) para enviar datos reales

Ejemplo con Formspree:

```javascript
fetch('https://formspree.io/f/your-form-id', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify(data)
})
```

### 8. Optimización de Imágenes

Antes de subir imágenes:
- Usa formatos modernos (WebP, AVIF)
- Comprime las imágenes (TinyPNG, Squoosh)
- Tamaños recomendados:
  - Hero: 1200x800px
  - Productos: 600x600px
  - Galería: 800x600px

### 9. Agregar Google Analytics

Antes de `</head>` en `index.html`, agrega:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### 10. Configurar SEO

Modifica los meta tags en `index.html` (líneas 6-7):

```html
<meta name="description" content="Descripción detallada de tu empresa y productos">
<meta name="keywords" content="palabra1, palabra2, palabra3">
```

## 📝 Notas Adicionales

- **Fuentes**: La página usa las fuentes del sistema (Apple System Font). Para fuentes personalizadas, agrega `@import` en `main.css`
- **Animaciones**: Puedes ajustar la velocidad en `main.css` (variables `--transition-*`)
- **Espaciado**: Modifica las variables `--spacing-*` para cambiar el espaciado general

## 🚀 Próximos Pasos

1. Reemplaza todos los placeholders con contenido real
2. Agrega tus imágenes optimizadas
3. Personaliza colores y textos
4. Configura el formulario de contacto
5. Prueba en diferentes dispositivos
6. Sube a GitHub Pages

¡Buena suerte con tu página web! 🎉

