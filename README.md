# Zomboid Builds v42.18.0

Una aplicación web moderna para crear y gestionar builds de personajes en Project Zomboid. Esta herramienta permite a los jugadores diseñar sus personajes de manera intuitiva, gestionando profesiones, rasgos positivos y negativos, y calculando automáticamente las habilidades resultantes.

https://zomboidbuilds.vercel.app/

![zomboidbuild-es](https://github.com/user-attachments/assets/6f7cc283-e88d-4c2f-86ac-af26eaeed9ac)

## 🎮 ¿Qué es Zomboid Builds?

Zomboid Builds es una aplicación web que simplifica el proceso de creación de personajes en Project Zomboid. En lugar de usar la interfaz del juego, los jugadores pueden:

- **Seleccionar profesiones** con sus habilidades base
- **Elegir rasgos positivos y negativos** con un sistema de compatibilidad inteligente
- **Ver las habilidades finales** calculadas automáticamente
- **Guardar y compartir builds** para uso posterior o con otros jugadores
- **Generar builds aleatorias** para experimentar con diferentes combinaciones

## 🚀 Características Principales

### 🎯 Gestión Inteligente de Builds
- **Sistema de compatibilidad**: Filtrado automático de rasgos incompatibles
- **Cálculo automático**: Habilidades calculadas en tiempo real
- **Validación de puntos**: Control de puntos restantes para equilibrar builds
- **Modos de juego**: Soporte para Individual y Multijugador con restricciones específicas

### 💾 Persistencia y Compartir
- **Guardado automático**: Estado persistente en localStorage
- **URLs compartibles**: Genera enlaces para compartir builds
- **Gestión de builds**: Guardar, cargar y eliminar builds personalizadas
- **Exportación PDF**: Genera reportes profesionales de builds

### 🎵 Experiencia de Usuario
- **Sistema de audio**: Efectos de sonido y música de fondo
- **Interfaz responsive**: Optimizada para móviles y escritorio
- **Internacionalización**: Soporte completo en Español e Inglés
- **Diseño moderno**: UI limpia y intuitiva con Tailwind CSS

### 🔧 Arquitectura Técnica
- **Lazy loading**: Carga optimizada de componentes
- **Hooks personalizados**: Lógica modular y reutilizable
- **Configuración centralizada**: Fácil mantenimiento y actualizaciones
- **Ofuscación de código**: Múltiples niveles de protección

## 🏗️ Arquitectura del Proyecto

### Estructura de Carpetas

```
src/
├── components/           # Componentes React organizados por funcionalidad
│   ├── features/        # Funcionalidades específicas
│   │   ├── build-management/  # Gestión de builds
│   │   ├── export/           # Exportación de datos
│   │   └── media/            # Sistema de audio
│   ├── game/           # Componentes del juego
│   │   ├── controls/         # Controles de interfaz
│   │   ├── skills/           # Visualización de habilidades
│   │   └── traits/           # Gestión de rasgos
│   └── ui/             # Componentes de interfaz
│       ├── buttons/          # Botones reutilizables
│       ├── layout/           # Componentes de layout
│       └── modals/           # Ventanas modales
├── hooks/              # Hooks personalizados organizados por dominio
│   ├── core/           # Hooks principales del juego
│   ├── traits/         # Lógica de rasgos y profesiones
│   ├── ui/             # Hooks de interfaz de usuario
│   ├── build/          # Gestión de builds
│   └── utils/          # Utilidades generales
├── config/             # Configuración centralizada
├── db/                 # Datos del juego (profesiones, rasgos)
├── locales/            # Archivos de traducción
└── utils/              # Utilidades generales
```

### Componentes Clave

#### 🎮 Componentes del Juego
- **ProfessionsList**: Lista interactiva de profesiones disponibles
- **PositiveTraitsList/NegativeTraitsList**: Gestión de rasgos con filtrado inteligente
- **SelectedTraitsList**: Visualización de rasgos seleccionados
- **SkillsList**: Muestra habilidades combinadas calculadas

#### 🎵 Sistema de Audio
- **MusicController**: Control flotante de música de fondo
- **ClickableButton/ClickableDiv**: Componentes con efectos de sonido integrados

#### 📱 Interfaz de Usuario
- **Navbar**: Navegación principal con enlaces sociales
- **Footer**: Controles y botones de acción
- **Modales**: Ventanas para guardar, confirmar y mostrar información

### Hooks Personalizados

#### 🧠 Lógica del Juego
- **useGameState**: Estado principal del juego (profesión, rasgos, modo)
- **useGameLogic**: Cálculos de habilidades y puntos
- **useTraitsLogic**: Sistema de compatibilidad entre rasgos

#### 🎯 Gestión de Builds
- **useBuildManager**: Gestión de builds guardadas y modales
- **useBuildOperations**: Operaciones de guardar/cargar builds
- **useDeleteOperations**: Eliminación de builds

#### 🎨 Interfaz de Usuario
- **useClickSound**: Efectos de sonido para interacciones
- **useBackgroundMusic**: Control de música de fondo
- **useToastManager**: Notificaciones del sistema

#### 🔧 Utilidades
- **useShareableURL**: Generación de URLs compartibles
- **useDataUtils**: Utilidades para manejo de datos
- **useStateUtils**: Utilidades para manejo de estado

## 🛠️ Tecnologías Utilizadas

### Frontend
- **React 19.1.0**: Framework de interfaz de usuario
- **Vite 7.0.4**: Herramienta de build y servidor de desarrollo
- **Tailwind CSS 4.1.11**: Framework de estilos utilitarios

### Funcionalidades
- **i18next 25.3.2**: Sistema de internacionalización
- **jsPDF 3.0.1**: Generación de documentos PDF
- **html2canvas 1.4.1**: Captura de pantalla para PDFs
- **react-toastify 11.0.5**: Sistema de notificaciones

### Desarrollo
- **ESLint**: Linting de código
- **javascript-obfuscator**: Ofuscación de código para producción
- **terser**: Minificación de código

## 🎵 Sistema de Audio

### Efectos de Sonido
- **Clics rotativos**: Tres sonidos diferentes que cambian automáticamente
- **Sonido de guardado**: Efecto especial al guardar builds
- **Volumen controlado**: Todos los efectos al 50% de volumen

### Música de Fondo
- **Música ambiental**: "Finally Calm" en bucle
- **Control de volumen**: Slider de 0-100%
- **Reproducción/pausa**: Control manual de la música
- **Volumen bajo por defecto**: 10% para no ser intrusivo

## 🌐 Internacionalización

La aplicación soporta múltiples idiomas usando i18next:

- **Español** (idioma por defecto)
- **Inglés** (traducción completa)

Los archivos de traducción se encuentran en `src/locales/` y se cargan dinámicamente.

## 💾 Sistema de Persistencia

La aplicación guarda automáticamente en localStorage:

- **Estado actual del juego**: Profesión, rasgos, modo
- **Builds guardadas**: Lista completa de builds personalizadas
- **Configuración**: Idioma, volumen, preferencias de audio

## 🔒 Ofuscación de Código

El proyecto incluye múltiples niveles de ofuscación para proteger el código en producción:

- **build:obfuscated**: Ofuscación estándar
- **build:basic**: Ofuscación básica
- **build:high**: Ofuscación alta
- **build:components**: Ofuscación específica de componentes
- **build:utilities**: Ofuscación específica de utilidades

## 🎮 Funcionalidades del Juego

### Creación de Personajes
- **Selección de profesiones**: Elige entre diversas profesiones con habilidades únicas de inicio
- **Gestión de rasgos**: Selecciona rasgos positivos y negativos con filtrado inteligente
- **Cálculo de habilidades**: Cálculo automático de habilidades combinadas desde profesión y rasgos
- **Balance de puntos**: Validación en tiempo real de puntos de rasgos restantes

### Gestión de Builds
- **Guardar builds**: Almacena builds de personajes personalizadas con nombres descriptivos
- **Cargar builds**: Acceso rápido a builds previamente guardadas
- **Eliminar builds**: Remueve builds no deseadas del almacenamiento
- **Generación aleatoria**: Genera builds aleatorias para experimentación

### Compartir y Exportar
- **URLs compartibles**: Genera enlaces para compartir builds con otros jugadores
- **Exportación PDF**: Crea reportes profesionales de builds con capturas de pantalla
- **Información de builds**: Visualiza información detallada de builds compartidas

### Modos de Juego
- **Individual**: Acceso a todos los rasgos y profesiones
- **Multijugador**: Restringido solo a rasgos compatibles con multijugador

## 🔧 Optimizaciones de Rendimiento

### Lazy Loading
- **Optimización de componentes**: Los componentes se cargan solo cuando se necesitan
- **Bundle inicial reducido**: Tamaño de descarga inicial más pequeño
- **Inicio más rápido**: Tiempo de inicio de aplicación mejorado

### Gestión de Estado
- **Actualizaciones eficientes**: Re-renderizados mínimos con actualizaciones de estado optimizadas
- **Gestión de memoria**: Limpieza adecuada de event listeners y timers
- **Almacenamiento local**: Persistencia de datos eficiente sin requerimientos de servidor

### Sistema de Audio
- **Sonidos precargados**: Archivos de audio cargados para reproducción instantánea
- **Control de volumen**: Control individual para efectos y música de fondo
- **Monitoreo de rendimiento**: Sistema de audio optimizado para reproducción fluida

## 📱 Experiencia de Usuario

### Diseño Responsive
- **Optimizado para móviles**: Funcionalidad completa en dispositivos móviles
- **Mejorado para escritorio**: Interfaz rica para usuarios de escritorio
- **Amigable al tacto**: Optimizado para interacciones táctiles

### Accesibilidad
- **Navegación por teclado**: Soporte completo de teclado para todas las funciones
- **Soporte para lectores de pantalla**: Etiquetas ARIA apropiadas y HTML semántico
- **Alto contraste**: Jerarquía visual clara y texto legible

### Interfaz de Usuario
- **Diseño moderno**: Interfaz limpia e intuitiva usando Tailwind CSS
- **Estilo consistente**: Lenguaje de diseño unificado en toda la aplicación
- **Retroalimentación visual**: Respuesta inmediata para todas las interacciones del usuario

## 📄 Licencia

Este proyecto está bajo la Licencia MIT.

## 🤝 Contacto y Soporte

- **Discord**: [https://discord.gg/d5yy6jHQJr](https://discord.gg/d5yy6jHQJr)
- **Twitter**: [@ElSantanax](https://x.com/ElSantanax)
- **PayPal**: [https://paypal.me/ElSantanax](https://paypal.me/ElSantanax)

---

**Versión**: v42.18.0-refactor  
**Última actualización**: 2026
