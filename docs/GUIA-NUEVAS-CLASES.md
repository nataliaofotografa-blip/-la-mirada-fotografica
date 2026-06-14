# Guía: Cómo Agregar Nueva Clase

## 📋 Checklist Rápido

- [ ] Crear carpeta `img/clase-X/`
- [ ] Optimizar y subir imágenes
- [ ] Crear `data/clase-X-imagenes.json`
- [ ] Crear `clase-X-tema.html`
- [ ] Agregar link en `index.html`
- [ ] Hacer commit y push

---

## 1️⃣ Preparar las Imágenes

### 1.1 Organizar Imágenes Localmente
```
Tu-carpeta-descarga/
├── imagen-1-original.jpg
├── imagen-2-original.jpg
└── ... más imágenes
```

### 1.2 Optimizar para Web
```bash
# Comando para comprimir (si tienes ImageMagick)
convert imagen.jpg -quality 85 -resize 1200x imagen-optimizada.jpg

# O usar online: tinypng.com, compressor.io
# Objetivo: <500KB por imagen
```

### 1.3 Renombrar Según Convención
```
[modulo]-[descriptor].jpg

Ejemplos para Clase 3 (Retrato):
- retrato-iluminacion-lateral.jpg
- retrato-ojos-enfocados.jpg
- retrato-fondo-desenfocado.jpg
- retrato-contraste-piel.jpg
```

### 1.4 Subir a la Carpeta
```bash
# En el proyecto
mkdir -p img/clase-3
# Copiar imágenes: img/clase-3/[archivos].jpg
```

---

## 2️⃣ Crear Metadata JSON

### 2.1 Template Base
```json
{
  "clase": 3,
  "titulo": "Retrato Fotográfico",
  "modulos": [
    {
      "id": "iluminacion",
      "nombre": "Iluminación en Retrato",
      "imagenes": [
        {
          "id": "iluminacion-frontal",
          "titulo": "Iluminación frontal",
          "local": "img/clase-3/retrato-iluminacion-frontal.jpg",
          "credito": "Natalia Olivera - Amapola Fotografía",
          "cc": true,
          "tema": "técnica de iluminación"
        }
      ]
    }
  ],
  "referencias_externas": [
    {
      "fuente": "Tu-fuente-principal",
      "urls": ["https://ejemplo.com/articulo"],
      "licencia": "CC BY-SA"
    }
  ],
  "actualizacion": "2026-06-XX",
  "version": "1.0"
}
```

### 2.2 Estructura de Módulos
```json
{
  "id": "identificador-unico",
  "nombre": "Nombre del Módulo",
  "descripcion": "Breve descripción",
  "imagenes": [
    {
      "id": "id-imagen",
      "titulo": "Título de la imagen",
      "local": "ruta/relativa.jpg",
      "credito": "Autor - Crédito",
      "cc": true,
      "tema": "subtema",
      "anotaciones": false,
      "descripcion": "Explicación de qué muestra"
    }
  ]
}
```

### 2.3 Guardar
```
/data/clase-3-imagenes.json
```

---

## 3️⃣ Crear HTML de la Clase

### 3.1 Usar Template Existente
Copiar estructura de `clase-2-composicion.html` como base:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <!-- COPIAR estilos de clase-2-composicion.html -->
  <title>Clase 3: Tu Tema · La Mirada Fotográfica</title>
</head>
<body>
  <!-- COPIAR header y nav -->
  
  <main class="wrap">
    <div class="hero">
      <span class="hero-tag">Clase 3</span>
      <h1>Tu Tema</h1>
      <p>Descripción breve de la clase</p>
    </div>
    
    <div class="intro-box">
      <div class="intro-t">¿Qué es [el tema]?</div>
      <div class="intro-d">Explicación introductoria</div>
    </div>
    
    <div class="mod-list" id="mod-container"></div>
  </main>
  
  <!-- COPIAR footer y nav -->
  
  <script>
  var CLASES_DATA = [
    {
      name: 'Módulo 1',
      desc: 'Descripción',
      topics: [
        {
          t: 'Subtema 1',
          h: '<div class="tp">Contenido...</div><img src="img/clase-3/imagen.jpg" alt="..." class="topic-img">'
        }
      ]
    }
    // ... más módulos
  ];
  
  // COPIAR función renderContent()
  </script>
</body>
</html>
```

### 3.2 Variables Importantes
```javascript
// En el HTML:
<span class="hero-tag">Clase 3</span>  // Actualizar número
<h1>Tu Tema</h1>                        // Actualizar tema
<div class="brand-sub">Amapola · Tu Tema</div>  // En header

// En JS:
{name:'Nombre Módulo', desc:'Descripción corta'...}
```

### 3.3 Integrar Imágenes
```html
<!-- En cada topic.h, agregar imagen -->
<img src="img/clase-3/nombre-imagen.jpg" alt="Descripción" class="topic-img">

<!-- Ejemplo completo -->
{
  t: 'Iluminación Frontal',
  h: '<div class="tp">Es la más simple...</div>' +
     '<img src="img/clase-3/retrato-frontal.jpg" alt="Iluminación frontal" class="topic-img">' +
     '<div class="tp">Ventajas: luz pareja...</div>'
}
```

### 3.4 Guardar
```
/clase-3-tu-tema.html
```

---

## 4️⃣ Registrar en Index.html

### 4.1 Agregar Link en Nav
En `index.html`, buscar sección de módulos y agregar:

```html
<!-- En la sección de CLASES o MÓDULOS -->
<div class="mod">
  <div class="mod-head" onclick="location.href='clase-3-tu-tema.html'">
    <div class="mod-num">03</div>
    <div class="mod-info">
      <div class="mod-name">Tu Tema</div>
      <div class="mod-desc">Descripción breve de la clase</div>
    </div>
  </div>
</div>
```

---

## 5️⃣ Hacer Commit

```bash
git add .
git commit -m "Agregar Clase 3: Tu Tema

- Crear estructura clase-3 con 8 módulos
- Integrar 12 imágenes educativas
- Documentación de fuentes (dZoom, etc)
- Referencias a Mobile Photo Awards

https://claude.ai/code/session_XXX"

git push -u origin claude/gallant-wright-jnfnj8
```

---

## 🎯 Checklist de Calidad

Antes de hacer commit, verificar:

- [ ] Todas las imágenes <500KB
- [ ] Nombres de archivos en snake-case (sin espacios)
- [ ] JSON válido (probar en jsonlint.com)
- [ ] Links de imágenes correctos en HTML
- [ ] Header y nav idénticos a otras clases
- [ ] CSS se carga correctamente
- [ ] Responsive (revisar en móvil)
- [ ] Créditos y licencias incluidos
- [ ] No hay archivos temporales (.tmp, .bak)
- [ ] Git status limpio antes de push

---

## 💡 Consejos Profesionales

### Para Imágenes
- ✅ Usar fotos reales de ejemplos
- ✅ Incluir anotaciones cuando eduquen
- ✅ Mantener consistencia visual (misma paleta)
- ✅ Imágenes con sujeto claro

### Para Contenido
- ✅ Párrafos cortos (<100 palabras por topic)
- ✅ Ejemplos prácticos y aplicables
- ✅ Referencias a fuentes educativas
- ✅ Lenguaje amable pero profesional

### Para Estructura
- ✅ 8-10 módulos por clase (máx)
- ✅ 2-3 subtemas por módulo
- ✅ 1-2 imágenes por subtema
- ✅ Progresión lógica de temas

---

## 🆘 Troubleshooting

### "Las imágenes no cargan"
```
Verificar:
1. Ruta correcta: img/clase-X/nombre.jpg
2. Archivo existe en esa ruta
3. Nombre sin espacios ni caracteres especiales
4. Extensión correcta (.jpg, .png)
```

### "El JSON da error"
```
Verificar:
1. Comillas dobles (no simples)
2. Sin comas en el último elemento
3. Usar jsonlint.com para validar
4. No hay caracteres especiales sin escape
```

### "Estilos CSS no aplican"
```
Verificar:
1. <link> del CSS está antes de </head>
2. Ruta correcta del CSS
3. No hay typos en nombres de clase
4. Limpiar caché del navegador (Ctrl+F5)
```

---

## 📧 Contacto / Soporte

Para preguntas sobre la estructura:
- Email: nataliaofotografa@gmail.com
- WhatsApp: 2266 549788

---

**Última actualización:** 14 de junio, 2026  
**Versión:** 1.0
