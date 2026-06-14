# Estructura del Proyecto - La Mirada Fotográfica

## 📁 Organización de Carpetas

```
/home/user/-la-mirada-fotografica/
├── index.html                    # Landing page principal (Academia)
├── clase-2-composicion.html      # Clase 2: Composición y Encuadre
├── composicion-encuadre.html     # Guía alternativa (en desarrollo)
├── iso-guia.html                 # Clase 1: ISO y Controles
│
├── img/
│   ├── clase-2/                  # Imágenes educativas de Clase 2
│   │   ├── hoja-roja-baldosa.jpg
│   │   ├── vendedor-milho-encuadre.jpg
│   │   ├── vendedor-frutas-accion.jpg
│   │   ├── regla-tercios-anotada-1.jpg
│   │   ├── regla-tercios-anotada-2.jpg
│   │   ├── pasillo-bn-profundidad.jpg
│   │   ├── barco-pared-minimalismo.jpg
│   │   ├── persona-vela-espacio.jpg
│   │   ├── personas-playa-palmeras.jpg
│   │   ├── barcos-repeticion.jpg
│   │   ├── espirales-arena-patrones.jpg
│   │   ├── edificios-bn-luz.jpg
│   │   ├── buzo-movimiento-accion.jpg
│   │   └── vendedores-equipos-naranjas.jpg
│   └── clase-X/                  # Futuras clases
│
├── data/
│   ├── clase-2-imagenes.json     # Metadatos de imágenes Clase 2
│   └── clase-X-imagenes.json     # Futuras clases
│
├── docs/
│   ├── ESTRUCTURA-PROYECTO.md    # Este archivo
│   ├── GUIA-NUEVAS-CLASES.md    # Cómo agregar nuevas clases
│   └── API-IMAGENES.md           # Documentación de uso de imágenes
│
└── .git/                          # Control de versiones
```

## 📚 Clases Disponibles

### Clase 1: ISO y Controles de Cámara
- **Archivo:** `iso-guia.html`
- **Enfoque:** Controles técnicos (ISO, velocidad, diafragma)
- **Público:** Principiantes técnicos
- **Imágenes:** Diagramas SVG + ejemplos

### Clase 2: Composición y Encuadre
- **Archivo:** `clase-2-composicion.html`
- **Enfoque:** Reglas de composición visual
- **Público:** Fotógrafos en desarrollo
- **Imágenes:** 14 imágenes educativas de Natalia Olivera
- **Metadatos:** `data/clase-2-imagenes.json`

## 🎨 Sistema de Imágenes

### Convención de Nombres
```
[modulo]-[descriptor].[extensión]
Ejemplos:
- hoja-roja-baldosa.jpg          (Centro de Interés)
- regla-tercios-anotada-1.jpg    (Regla de Tercios)
- edificios-bn-luz.jpg           (Luz y Composición)
```

### Metadata JSON (Estructura)
```json
{
  "id": "identificador-unico",
  "titulo": "Título descriptivo",
  "local": "ruta/al/archivo.jpg",
  "credito": "Autor - Atribución",
  "cc": true,
  "tema": "tema compositivo",
  "anotaciones": false
}
```

### Optimización de Imágenes
- **Formato:** JPG para fotografías, PNG para diagramas
- **Tamaño máximo:** 500KB (optimizado para móvil)
- **Resolución:** 1200px ancho máximo
- **Compresión:** Quality 85% (balance óptimo)

## 🔄 Flujo de Datos (Front-end + Back-end Ready)

```
HTML (clase-2-composicion.html)
    ↓
Lee referencias de imágenes
    ↓
JavaScript genera módulos dinámicamente
    ↓
Carga imágenes desde /img/clase-2/
    ↓
Renderiza con CSS responsive
```

### Escalabilidad Futura
La arquitectura soporta:
- ✅ Agregar imágenes sin modificar HTML
- ✅ Cargar datos desde API (próxima versión)
- ✅ Múltiples idiomas (data separada por idioma)
- ✅ Sistema de progreso del estudiante (back-end ready)

## 📝 Fuentes y Créditos

### Contenido Educativo
- **dZoom.org.es** (5 artículos sobre composición)
- **Mobile Photo Awards** (inspiración de fotógrafos ganadores)
- **Natalia Olivera** (fotografías y ejemplos)

### Licencias
- Todas las imágenes originales: CC BY-SA (uso educativo)
- Créditos incluidos en metadata

## 🚀 Para Agregar Nueva Clase

1. **Crear carpeta:** `img/clase-X/`
2. **Subir imágenes:** Seguir convención de nombres
3. **Crear JSON:** `data/clase-X-imagenes.json`
4. **Crear HTML:** `clase-X-tema.html`
5. **Registrar en index.html:** Agregar link a nueva clase
6. **Documentar:** Agregar entrada en este archivo

Ver `GUIA-NUEVAS-CLASES.md` para instrucciones detalladas.

## 🔒 Versionado

- **Rama principal:** `main`
- **Rama desarrollo:** `claude/gallant-wright-jnfnj8`
- **Commits:** Incluyen session ID de Claude para trazabilidad

---

**Última actualización:** 14 de junio, 2026  
**Mantenedor:** Natalia Olivera - Amapola Fotografía
