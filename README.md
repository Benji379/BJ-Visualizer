# Guía de Distribución de Archivos - BJ Visualizer

Este proyecto es un visualizador dinámico de mapas jerárquicos (Mundo y Perú) construido con Leaflet. Este recurso le puede servir a cualquier persona que quiera integrar mapas interactivos, navegación geográfica por niveles o manejo de datos GeoJSON en sus proyectos.

Este documento detalla la organización de los archivos y carpetas del proyecto para asegurar un funcionamiento fluido del visualizador de mapas.

## 📂 Estructura Principal

El proyecto está organizado para separar la lógica de visualización (HTML/JS) de los datos geográficos (JSON).

### 📍 Directorio Raíz
- **index.html**: El corazón de la aplicación. Contiene la estructura, los estilos (CSS) y la lógica (JavaScript) para renderizar los mapas usando Leaflet.
- **DOCUMENTACION.md**: Este archivo explicativo.

---

## 🌎 Directorio `GLOBAL/`
Esta carpeta contiene los archivos esenciales de configuración y los mapas base que se cargan al iniciar la aplicación.

1. **`mapeo_general_ubicaciones.json`**:
   - **Propósito**: Es el "cerebro" del sistema. Mapea cada ubicación (Región, Provincia, Distrito, País) con su respectivo archivo JSON local.
   - **Uso**: Permite que al hacer clic en una región como "Áncash", el sistema sepa exactamente qué archivo cargar para mostrar sus provincias.

2. **`mundo.json`**:
   - **Propósito**: Contiene la geometría (GeoJSON) de todos los países del mundo.
   - **Uso**: Es el mapa que ves por defecto al entrar a la aplicación ("Vista TODOS").

3. **`peruLow.json`**:
   - **Propósito**: Contiene los límites de los 25 departamentos (regiones) del Perú.
   - **Uso**: Se carga automáticamente cuando seleccionas "PERÚ" en el selector principal.

4. **`continental_total.json`**:
   - **Propósito**: Datos geográficos agrupados por continentes.
   - **Uso**: Sirve como base para la navegación internacional fuera del Perú.

5. **`favicon.ico`**:
   - **Propósito**: El icono oficial de la aplicación (**BJ Visualizer**).
   - **Uso**: Aparece en la pestaña del navegador y en el logo del encabezado.

---

## 🏛️ Directorio `PERÚ/`
Contiene la jerarquía detallada del territorio nacional organizada por carpetas:
- **Nivel 1**: Regiones (ej. `ÁNCASH/`, `LIMA/`).
- **Nivel 2**: Provincias (dentro de cada región).
- **Nivel 3**: Archivos `.json` individuales por provincia que contienen los límites de sus distritos.

## ✈️ Directorio `EXTRANJERO/`
Contiene la información de países y ciudades fuera del Perú, organizada por continentes:
- **Estructura**: `Continente > País > Archivos JSON` con los límites de las ciudades principales.

---

### Notas de Mantenimiento
- Si se agregan nuevos archivos JSON de distritos, deben registrarse en `GLOBAL/mapeo_general_ubicaciones.json` para que el buscador pueda localizarlos.
- Los nombres en los archivos JSON deben estar normalizados (Mayúsculas y sin caracteres especiales extraños) para asegurar que el sistema de búsqueda los detecte correctamente.

visita mi pagina [benjicode.com](https://benjicode.com)

Gracias ONPE ;)
