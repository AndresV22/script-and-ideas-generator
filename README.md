# 🎬 Generador de Contenido YouTube con Ollama

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML](https://img.shields.io/badge/HTML-5-orange.svg)](https://www.w3.org/html/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![React](https://img.shields.io/badge/React-18-blue.svg)](https://reactjs.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC.svg)](https://tailwindcss.com/)

Un generador de contenido profesional para YouTube que utiliza modelos de IA locales con Ollama. Genera títulos, descripciones, guiones, tags, comentarios fijados y posts para la comunidad, todo optimizado para SEO y engagement.

## ✨ Características

- 🤖 **Generación con IA Local**: Utiliza Ollama para generar contenido sin depender de APIs externas
- 📝 **Templates Especializados**: Plantillas optimizadas para diferentes tipos de contenido (reseñas, gaming, educativo, etc.)
- 🌍 **Multiidioma**: Soporte completo para español e inglés
- 📊 **Contenido Completo**: Genera títulos, thumbnails, descripción SEO, tags, comentario fijado, post de comunidad y guión
- ⚡ **Tiempo Real**: Visualiza la generación de contenido en tiempo real
- 📄 **Exportación**: Descarga en formato TXT o PDF profesional
- ✏️ **Edición**: Editor integrado para modificar todos los resultados
- 🎮 **Mini-juegos**: Pong integrado para entretenerse durante la generación
- 🎯 **Tips Inteligentes**: Sistema de consejos aleatorios para mejorar el uso

## 🚀 Instalación Rápida

### Paso 1: Preparar el Entorno de Desarrollo

1. **Instalar Visual Studio Code**
   ```bash
   # Descargar desde: https://code.visualstudio.com/
   ```

2. **Instalar la extensión Live Server**
   - Abrir VS Code
   - Ir a Extensions (Ctrl+Shift+X)
   - Buscar "Live Server" por Ritwick Dey
   - Hacer clic en "Install"

3. **Ejecutar la aplicación**
   - Abrir el archivo `index.html` en VS Code
   - Hacer clic en "Go Live" en la esquina inferior derecha
   - La aplicación se abrirá automáticamente en tu navegador

### Paso 2: Configurar Ollama

1. **Instalar Ollama**
   ```bash
   # macOS
   brew install ollama
   
   # Linux
   curl -fsSL https://ollama.com/install.sh | sh
   
   # Windows
   # Descargar desde: https://ollama.com/download/windows
   ```

2. **Iniciar el servicio Ollama**
   ```bash
   ollama serve
   ```

3. **Descargar modelos recomendados**
   ```bash
   # Modelo principal (mejor para español)
   ollama pull gemma3n:e4b
   
   # Modelos alternativos
   ollama pull mistral:7b
   ollama pull mistral-nemo:12b
   ```

## 📋 Requisitos del Sistema

- **Sistema Operativo**: Windows 10+, macOS 10.15+, Linux
- **RAM**: Mínimo 8GB (16GB recomendado)
- **Almacenamiento**: 10GB libres para modelos
- **Navegador**: Chrome, Firefox, Safari, Edge (versiones recientes)
- **Ollama**: Versión 0.1.0 o superior

## 🎯 Guía de Uso

### Configuración Inicial

1. **Paso 1 - Configuración**
   - Selecciona el idioma del contenido
   - Elige la categoría del video
   - Opcionalmente, selecciona un template especializado
   - Ajusta la URL de Ollama (por defecto: `http://localhost:11434/api/generate`)

2. **Paso 2 - Detalles del Contenido**
   - Define el tema específico del video (máx. 100 caracteres)
   - Agrega datos clave para mayor precisión
   - Selecciona el estilo del guión
   - Proporciona el nombre del canal
   - Enlaza un video relacionado (opcional)

3. **Paso 3 - Generación y Resultados**
   - Observa la generación en tiempo real
   - Edita los resultados si es necesario
   - Exporta en TXT o PDF

### Templates Disponibles

- **Reseñas de Relojes/Tecnología**: Estructura optimizada para reviews
- **Contenido Educativo**: Para tutoriales y explicaciones
- **Maquillaje y Belleza**: Tutoriales de makeup y skincare
- **Moda y Estilo**: Outfits y consejos de estilo
- **Gaming**: Reviews de juegos y gameplay
- **Estilo de Vida**: Vlogs y rutinas diarias
- **Personalizado**: Define tu propia estructura

## 🛠️ Troubleshooting

### Error de JSON Malformateado

Si aparece un error al procesar el JSON generado:

1. **Editor Manual Automático**
   - El sistema detecta automáticamente errores de formato
   - Se abre el editor manual con el contenido generado
   - Puedes corregir el JSON manualmente

2. **Formato Esperado**
   ```json
   {
     "titles": ["Título 1", "Título 2", "Título 3", "Título 4", "Título 5"],
     "thumbnails": ["Frase 1", "Frase 2", "Frase 3", "Frase 4", "Frase 5"],
     "description": "Descripción SEO optimizada...",
     "tags": ["tag1", "tag2", "tag3", "...", "tag20"],
     "pinnedComment": "Comentario fijado sugerido...",
     "communityPost": "Post para Community Tab...",
     "script": "Guión completo aquí..."
   }
   ```

3. **Errores Comunes y Soluciones**
   - **Comillas sin escapar**: Cambiar `"` por `\"`
   - **Saltos de línea**: Reemplazar saltos reales con `\n`
   - **Comas finales**: Eliminar comas antes de `}` o `]`

### Problemas de Conexión con Ollama

1. **Verificar que Ollama esté ejecutándose**
   ```bash
   # Verificar proceso
   ps aux | grep ollama
   
   # Reiniciar si es necesario
   ollama serve
   ```

2. **Probar conexión manualmente**
   ```bash
   curl http://localhost:11434/api/generate \
     -d '{
       "model": "gemma3n:e4b",
       "prompt": "Hello world",
       "stream": false
     }'
   ```

3. **Verificar modelos disponibles**
   ```bash
   ollama list
   ```

### Problemas de Rendimiento

- **Generación lenta**: Reduce la ventana de contexto o usa un modelo más pequeño
- **Uso de memoria alto**: Cierra otras aplicaciones durante la generación
- **Errores de formato frecuentes**: Activa "Desactivar Pensamiento" para modelos compatibles

## ⌨️ Comandos y Atajos

| Comando | Función |
|---------|---------|
| `Cmd/Ctrl + H` | Mostrar información del creador |
| `Cmd/Ctrl + K` | Activar efecto Matrix (10 segundos) |
| `Cmd/Ctrl + P` | Abrir/cerrar juego Pong |
| `Cmd/Ctrl + D` | Modo desarrollador (datos de prueba) |

### Comandos de Ollama

```bash
# Gestión de modelos
ollama pull <modelo>          # Descargar modelo
ollama list                   # Listar modelos instalados
ollama rm <modelo>            # Eliminar modelo
ollama show <modelo>          # Mostrar información del modelo

# Servicio
ollama serve                  # Iniciar servidor
ollama ps                     # Ver modelos en ejecución
ollama stop <modelo>          # Detener modelo específico

# Uso directo
ollama run <modelo>           # Ejecutar modelo interactivamente
ollama run <modelo> "prompt"  # Ejecución directa con prompt
```

## 🤖 Modelos Recomendados

### Para Español
- **gemma3n:e4b** ⭐ (Recomendado)
  - Excelente calidad de contenido
  - Ocasionalmente problemas de formato JSON
  - Tamaño: ~4GB

### Para Inglés
- **mistral:7b**
  - Buen balance calidad/velocidad
  - Formato JSON más consistente
  - Tamaño: ~4GB

### Modelos Alternativos
- **mistral-nemo:12b**: Mayor calidad, más lento
- **llama3.2:3b**: Más rápido, menor calidad

## 📁 Estructura del Proyecto

```
youtube-generator/
├── index.html              # Aplicación principal
├── README.md               # Este archivo
└── screenshots/            # Capturas de pantalla (opcional)
```

## 🔧 Configuración Avanzada

### Personalizar URL de Ollama

Si Ollama está en otro servidor:
```javascript
// En la configuración
baseUrl: 'http://tu-servidor:11434/api/generate'
```

### Ajustar Ventana de Contexto

- **8000-12000**: Contenido corto, más rápido
- **16000-20000**: Contenido estándar (recomendado)
- **24000-32000**: Contenido muy detallado, más lento

### Optimizar Rendimiento

1. **Para equipos menos potentes**:
   - Usar modelos más pequeños (3B parámetros)
   - Reducir ventana de contexto a 8000-12000
   - Cerrar aplicaciones innecesarias

2. **Para equipos potentes**:
   - Usar modelos grandes (13B+ parámetros)
   - Aumentar ventana de contexto a 32000
   - Habilitar GPU si está disponible

## 🐛 Problemas Conocidos

- **gemma3n:e4b**: Ocasionalmente genera JSON malformateado (solucionable con editor manual)
- **Modelos grandes**: Pueden requerir mucha RAM en equipos limitados
- **Safari**: Algunos elementos CSS pueden verse ligeramente diferentes

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/nueva-caracteristica`)
3. Commit tus cambios (`git commit -am 'Agregar nueva característica'`)
4. Push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

## 📜 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👨‍💻 Autor

**AndresV22**
- GitHub: [@AndresV22](https://github.com/AndresV22)
- Email: [tu-email@ejemplo.com]

## 🙏 Agradecimientos

- [Ollama](https://ollama.com/) por la increíble plataforma de IA local
- [Tailwind CSS](https://tailwindcss.com/) por el sistema de diseño
- [React](https://reactjs.org/) por la biblioteca de componentes
- [jsPDF](https://github.com/parallax/jsPDF) por la generación de PDFs

## 📊 Estadísticas

- **Líneas de código**: ~2,500
- **Componentes React**: 15+
- **Templates**: 8 especializados
- **Idiomas soportados**: 2
- **Formatos de exportación**: 2

---

⭐ **¡Si te gusta este proyecto, dale una estrella en GitHub!** ⭐