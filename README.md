# 📚 Robotics Academy - Documento Técnico

## 🎯 Descripción del Proyecto

Robotics Academy es una plataforma de e-learning moderna y completa diseñada para la enseñanza de robótica y tecnología. Desarrollada con React y tecnologías web de vanguardia, ofrece una experiencia de aprendizaje inmersiva con soporte para múltiples tipos de contenido (video, artículos, cuestionarios, proyectos) y seguimiento de progreso en tiempo real.

## 🏗️ Arquitectura del Proyecto

### Estructura de Carpetas

```
robotics-v2/
├── public/                     # Archivos estáticos
│   ├── data/
│   │   └── courses.json       # Datos de cursos
│   ├── img/                   # Imágenes del proyecto
│   └── models/               # Modelos 3D de robots
├── src/                       # Código fuente principal
│   ├── components/           # Componentes reutilizables
│   │   ├── Navigation/       # Navegación principal
│   │   ├── Hero/            # Sección hero
│   │   ├── Courses/         # Componentes de cursos
│   │   ├── Chatbot/         # Asistente virtual
│   │   ├── About/           # Sobre nosotros
│   │   └── Contact/         # Contacto
│   ├── pages/                # Vistas/páginas principales
│   │   ├── CoursesPage.jsx   # Catálogo de cursos
│   │   ├── CourseDetailPage.jsx # Detalle de curso
│   │   ├── LessonPage.jsx    # Vista de lección
│   │   ├── ProgressDashboard.jsx # Dashboard de progreso
│   │   ├── Login.jsx         # Página de login
│   │   └── Principal.jsx     # Página principal
│   ├── context/              # Gestión de estado global
│   │   └── CourseContext.jsx # Contexto de cursos y progreso
│   ├── hooks/                # Hooks personalizados
│   ├── App.jsx               # Componente principal
│   └── main.jsx              # Punto de entrada
├── vite.config.js            # Configuración de Vite
└── package.json              # Dependencias del proyecto
```

## 🛠️ Stack Tecnológico

### Frontend Core

* **React 19.1.0** - Biblioteca principal de UI

* **Vite 7.0.3** - Build tool y servidor de desarrollo

* **React Router DOM 7.9.5** - Enrutamiento SPA

### UI Framework & Estilos

* **Material-UI (MUI) 7.3.4** - Componentes UI predefinidos

* **Emotion** - CSS-in-JS para estilos dinámicos

* **CSS Personalizado** - Estilos con variables CSS y diseño futurista

### Iconos y Gráficos

* **Material Icons** - Iconografía principal

* **Lucide React** - Iconos adicionales

* **Tabler Icons** - Iconos complementarios

### 3D & Animaciones

* **Three.js** - Renderizado 3D

* **React Three Fiber** - Integración de Three.js con React

* **React Three Drei** - Utilidades para React Three Fiber

### Desarrollo

* **ESLint** - Linting y calidad de código

* **SWC** - Compilador rápido para React

## 🧩 Componentes Principales

### 1. **CourseContext** (`context/CourseContext.jsx`)

Gestión centralizada del estado de la aplicación:

* Carga de cursos desde JSON

* Gestión de progreso del usuario (localStorage)

* Funciones de inscripción y completado de lecciones

* Navegación entre lecciones

### 2. **CoursesPage** (`pages/CoursesPage.jsx`)

Catálogo principal de cursos:

* Hero section con diseño futurista

* Filtros por categoría y nivel

* Vista de cuadrícula/lista de cursos

* Tarjetas animadas con información del curso

### 3. **CourseDetailPage** (`pages/CourseDetailPage.jsx`)

Vista detallada del curso:

* Información completa del curso

* Lista de lecciones organizadas

* Sistema de inscripción

* Barra de progreso del estudiante

* Información del instructor

### 4. **LessonPage** (`pages/LessonPage.jsx`)

Visualización de lecciones individuales:

* Soporte para múltiples tipos de contenido

* Navegación entre lecciones

* Marcado de lecciones completadas

* Sidebar con lista de lecciones

### 5. **ProgressDashboard** (`pages/ProgressDashboard.jsx`)

Dashboard de seguimiento:

* Estadísticas generales del estudiante

* Progreso por curso

* Visualización de logros

## 🔄 Sistema de Rutas

```jsx
<Routes>
  <Route path="/" element={<CoursesPage />} />
  <Route path="/courses" element={<CoursesPage />} />
  <Route path="/courses/:courseId" element={<CourseDetailPage />} />
  <Route path="/courses/:courseId/lesson/:lessonId" element={<LessonPage />} />
  <Route path="/progress" element={<ProgressDashboard />} />
  <Route path="*" element={<CoursesPage />} /> {/* SPA Fallback */}
</Routes>
```

## 📊 Gestión de Datos

### Estructura de Datos (courses.json)

```json
{
  "courses": [
    {
      "id": "robotics-basics",
      "title": "Fundamentos de Robótica Moderna",
      "description": "Curso completo de robótica...",
      "category": "Robótica",
      "level": "beginner",
      "duration": "8 semanas",
      "rating": 4.8,
      "studentsEnrolled": 1250,
      "instructor": {
        "name": "Dr. Elena Martínez",
        "avatar": "/img/instructor1.jpg",
        "bio": "PhD en Robótica, 15 años de experiencia..."
      },
      "lessons": [
        {
          "id": "lesson-1",
          "title": "Introducción a la Robótica",
          "type": "video",
          "duration": 25,
          "description": "Conceptos fundamentales..."
        }
      ],
      "requirements": [...],
      "learningObjectives": [...]
    }
  ]
}
```

### Persistencia de Datos

* **localStorage**: Almacena el progreso del usuario

* **JSON estático**: Datos de cursos (simula API REST)

* **Context API**: Gestión de estado global sin dependencias externas

## 🎨 Sistema de Diseño

### Variables CSS (Paleta de Colores)

```css
:root {
  --absolute-black: #000000;
  --electric-blue: #10259E;
  --cyan: #00A295;
  --terracotta: #BE4600;
  --green-forest: #00553E;
  --green-zombie: #00FF00;
  --color-light: #ffffff;
  --color-dark: #1a1a1a;
}
```

### Tipografía

* **Zalando Sans Expanded**: Títulos principales

* **Oswald**: Textos y navegación

* **Saira**: Elementos UI

### Estilos de Componentes

* **Gradientes dinámicos**: Backgrounds con múltiples colores

* **Bordes luminosos**: Efectos de neón y brillo

* **Animaciones suaves**: Transiciones CSS y microinteracciones

* **Diseño responsivo**: Mobile-first con breakpoints adaptativos

## ⚡ Características Implementadas

### Funcionalidades Core

1. **Catálogo de Cursos**

   * Visualización en grid/lista

   * Filtros por categoría y nivel

   * Búsqueda por título

   * Tarjetas animadas con hover effects

2. **Sistema de Inscripción**

   * Inscripción a cursos con un clic

   * Gestión de estado de inscripción

   * Persistencia en localStorage

3. **Visualización de Lecciones**

   * Soporte para múltiples tipos de contenido

   * Navegación intuitiva entre lecciones

   * Marcado de progreso visual

   * Contenido bloqueado para no inscritos

4. **Seguimiento de Progreso**

   * Barra de progreso por curso

   * Estadísticas generales del estudiante

   * Lecciones completadas/marcadas

   * Tiempo estimado de estudio

5. **Diseño Futurista**

   * Interfaz moderna con estilo cibernético

   * Animaciones y transiciones fluidas

   * Paleta de colores coherente

   * Efectos visuales llamativos

### Características Técnicas

1. **SPA (Single Page Application)**

   * Navegación sin recargas

   * Gestión de rutas con React Router

   * Fallback para rutas no encontradas

2. **Estado Global con Context API**

   * Sin dependencias externas de estado

   * Gestión centralizada de datos

   * Actualización reactiva de componentes

3. **Persistencia Local**

   * localStorage para datos de usuario

   * Sincronización automática

   * Sin backend requerido

4. **Diseño Responsivo**

   * Adaptación a múltiples dispositivos

   * Mobile-first approach

   * Breakpoints optimizados

## 🚀 Instalación y Desarrollo

### Requisitos Previos

* Node.js 22.17.0 o superior

* npm o yarn

### Instalación

```bash
# Clonar el repositorio
git clone [url-del-repositorio]
cd robotics-v2

# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev
```

### Scripts Disponibles

```bash
npm run dev      # Servidor de desarrollo (http://localhost:5173)
npm run build    # Build para producción
npm run preview  # Vista previa del build
npm run lint     # Ejecutar linter
```

## 🔧 Decisiones Técnicas y Problemas Resueltos

### 1. **Elección de Stack Tecnológico**

**Decisión**: React + Vite + Context API
**Justificación**:

* React: Maturidad y ecosistema robusto

* Vite: Velocidad de desarrollo y build optimizado

* Context API: Simplicidad sin dependencias externas

### 2. **Gestión de Estado**

**Decisión**: Context API en lugar de Redux/Zustand
**Justificación**:

* Estado relativamente simple

* Sin necesidad de middleware complejo

* Menor bundle size

* Facilidad de mantenimiento

### 3. **Persistencia de Datos**

**Decisión**: localStorage + JSON estático
**Justificación**:

* No requiere backend para MVP

* Desarrollo y despliegue rápidos

* Datos siempre disponibles offline

* Fácil migración a backend futuro

### 4. **Problemas de Rendering Resueltos**

#### Error: "Objects are not valid as a React child"

**Problema**: Renderizado directo de objetos en JSX
**Solución**: Acceso a propiedades específicas con optional chaining

```jsx
// Antes (error):
<Typography>{course.instructor}</Typography>

// Después (correcto):
<Typography>{course.instructor?.name}</Typography>
```

#### Inconsistencia de Datos

**Problema**: Estructura JSON vs expectativas de componentes
**Solución**: Validación y fallbacks en componentes

```jsx
const instructorName = course.instructor?.name || course.instructor;
const studentCount = course.studentsEnrolled ?? course.enrolledStudents ?? 0;
```

### 5. **Routing SPA**

**Problema**: Páginas en blanco al recargar rutas no raíz
**Solución**:

* Ruta comodín en React Router

* Configuración de Vite con `historyApiFallback`

* Archivos de configuración para plataformas de despliegue

### 6. **Optimización de Rendimiento**

**Implementaciones**:

* Lazy loading de componentes (si es necesario)

* Memoización de cálculos pesados

* CSS modules para evitar conflictos de estilos

* Imágenes optimizadas y compresión de assets

## 📋 Próximos Pasos y Mejoras

### Funcionalidades Futuras

1. **Backend Integration**

   * API REST con autenticación real

   * Base de datos para cursos y usuarios

   * Sistema de certificados

2. **Características Avanzadas**

   * Foros de discusión por curso

   * Sistema de notificaciones

   * Modo oscuro/claro

   * Multi-idioma

3. **Mejoras de UX**

   * Animaciones más sofisticadas

   * Transiciones de página

   * Loading states mejorados

   * Accesibilidad completa

### Optimizaciones Técnicas

1. **Performance**

   * Code splitting avanzado

   * Service workers para offline

   * Optimización de imágenes

   * CDN para assets estáticos

2. **Testing**

   * Unit tests con Jest

   * Integration tests

   * E2E tests con Cypress

   * Coverage reports

## 📞 Soporte y Contacto

Para reportar problemas o sugerir mejoras:

* Crear un issue en el repositorio

* Contactar al equipo de desarrollo

* Revisar la documentación de componentes

***

**Robotics Academy** - Desarrollado con ❤️ para la comunidad de robótica y tecnología.

*Última actualización: 2025*
