# Guía de Distribución de Archivos - BJ Visualizer

Este proyecto es un visualizador dinámico de mapas jerárquicos (Mundo y Perú) construido con Leaflet. Este recurso le puede servir a cualquier persona que quiera integrar mapas interactivos, navegación geográfica por niveles o manejo de datos GeoJSON en sus proyectos.

### 🌐 Demo en Vivo
Puedes ver la aplicación funcionando aquí: **[https://benji379.github.io/BJ-Visualizer/](https://benji379.github.io/BJ-Visualizer/)**


Este documento detalla la organización de los archivos y carpetas del proyecto para asegurar un funcionamiento fluido del visualizador de mapas.

## 📂 Estructura Principal

El proyecto está organizado para separar la lógica de visualización (HTML/JS) de los datos geográficos (JSON).

<div align="center">
  <img width="800" alt="Vista Global" src="https://github.com/user-attachments/assets/3b4b4de5-7419-4e86-9d13-3275a5913f8e" />
  <img width="800" alt="Vista Perú" src="https://github.com/user-attachments/assets/0b279d5d-0959-4f81-beb6-edb1188ab065" />
  <img width="800" alt="Vista Detalle" src="https://github.com/user-attachments/assets/b6e8e01e-27e6-44b8-8a03-ca4547822096" />
</div>

### 🚀 Cómo Ejecutar

Para que la aplicación funcione correctamente y pueda cargar los archivos GeoJSON, **debes ejecutarla a través de un servidor local**. Abrir el archivo `index.html` directamente en el navegador causará errores de **CORS** (Cross-Origin Resource Sharing).

**Opciones recomendadas:**
- **VS Code**: Usa la extensión [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).
- **Python**: Ejecuta `python -m http.server` en la carpeta del proyecto.
- **Node.js**: Usa `npx serve .`

### 📍 Directorio Raíz
- **index.html**: El corazón de la aplicación. Contiene la estructura, los estilos (CSS) y la lógica (JavaScript) para renderizar los mapas usando Leaflet.
- **README.md**: Este archivo explicativo.

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
