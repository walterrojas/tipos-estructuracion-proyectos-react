# Tipos de Organización y Estructuración de Proyectos React

## ¿Cómo podemos organizar y estructurar un proyecto React?

Esta es una pregunta típica que nos hacemos cuando estamos creando un nuevo proyecto React o cuando estamos comenzando a trabajar en uno que ya existe e identificamos que se podría mejorar al re-organizarlo.

Cuando organizamos los archivos y carpetas dentro de un proyecto React de una manera conveniente, nos va a facilitar grandemente cuando necesitmos realizar mantenibilidad, escalabilidad y navegación. En este documento hablaremos sobre una arquitectura general y como poder estructuras las carpetas en base al tamaño de proyectos React

## 1) Organización por Tipos de Archivos ( _Recomendado para proyectos de tamaño pequeño a mediano_ )
Esta estructura se caracteriza por su simplicidad: agrupa los archivos por su tipo:

<img width="368" alt="1-estructuracion-por-tipo-archivos" src="https://github.com/user-attachments/assets/bf38c065-c77f-4ba9-b915-3aa73ccd628d" />

Este tipo de organización es usado para:

### Tamaño del proyecto:
Pequeño a mediano

### Ventajas:
Simple y directo

### Desventajas:
- Crecerá rápidamente y será difícil de mantener.
- No hay separación de logica comercial

Por ejemplo: tenemos que un proyecto que tiene bastante codigo relacionado con pagos. Un día, todo el negocio cambia y deja de ser necesario todo lo relacionado a pagos, ¿qué tan fácil es reemplazar o eliminar el codigo relacionado? Con esta estructura de carpetas, tendrás que revisar cada carpeta y sus archivos para realizar los cambios necesarios. Y si el proyecto sigue creciendo, pronto se convertirá en un dolor de cabeza para poder mantenerlo y el cual solo empeorará con el tiempo.

## 2) Organización por Tipos de Archivos y Features ( _Recomendado para proyectos de tamaño mediano a grande_ )
Para los casos en que los proyectos siguen creciendo, podemos usar este tipo de organizacación por features dentro de cada tipo de archivo

<img width="404" alt="2-estructuracion-por-tipo-archivos-y-features" src="https://github.com/user-attachments/assets/8859928c-1099-4a45-aa5f-e8fb07637aee" />

Este tipo de organización es usado para:

### Tamaño del proyecto:
Mediano a grande

### Ventajas:
- Simple y directo
- Las elementos están agrupados por features del proyecto

### Desventajas:
- La lógica relacionada con una función aún está distribuida entre varios tipos de carpetas

Por ejemplo: Volviendo al problema anterior, donde el módulo de pagos debe modificarse o eliminarse. Con esta estructura, es mucho más fácil hacerlo.
Esta estructura de carpetas es la que recomendaría si no sabes qué elegir.


## 3) Organización por Features o módulos ( _Recomendado para proyectos de tamaño grande y complejo_ )
Para proyectos más grandes, esta organización nos ofrece un enfoque altamente modular, definiendo límites claros para diferentes aspectos de la aplicación dentro de cada módulo:

<img width="344" alt="3-estructuracion-por-features-o-modulos" src="https://github.com/user-attachments/assets/c654144a-ad51-4133-b0ce-036b4c13a67d" />

Este tipo de organización es usado para:

### Tamaño del proyecto:
Grande y complejo

### Ventajas:
- Los elementos están claramente agrupados por features/módulos.
- Los features/módulos son representaciones claras de objetos en el mundo real.

### Desventajas:
- Se necesita conocer muy bien la lógica de la empresa para poder agrupar correctamente

Con este tipo de organización, si quieres eliminar o modificar la lógica de pagos, sabrás inmediatamente por dónde empezar


### Recomendaciones al definir los Nombres de Carpetas
Independientemente del nivel de estructura, los nombres de carpeta deben tener significados específicos. El significado de un nombre de carpeta puede variar según tus preferencias o las convenciones del proyecto, pero siempre se debe usar nombres que sean sumamente claros

Esto es lo que suelo recomendar para los nombres de las carpetas:

### UI Componentss o Componentes de la interfaz de usuario

#### Componentes (components):
Componentes de React: los principales elementos para comenzar a construir nuestras interfaz de usuario.

#### Sistema de diseño (design-system):
Elementos y patrones de interfaz de usuario fundamentales basados ​​en el sistema de diseño que nos proporciona el area de UI/UX o que no nosotros podemos proponer siguiente un design system actual

#### Iconos (icons):
Iconos SVG diseñados para usarse en directamente


### Elementos especificos de React

#### Hooks:
React hooks personalizados para contener una lógica compartida

#### HOCs:
Componentes de orden superior de React

#### Context/Providers:
Se refiere especificamente a contextos y proveedores de React

### Utilidades e integraciones externas

#### utils:
Utilidades para lógica universal que no está relacionada con la lógica empresarial ni con ninguna tecnología, por ejemplo, manipulaciones de cadenas, cálculos matemáticos, etc.

#### lib:
Utilidades relacionadas con ciertas tecnologías, por ejemplo, manipulaciones DOM, lógica relacionada con HTML, localStorage, IndexedDB, etc.

#### Plugins:
Plugins como por ejemplo, i18n, Sentry, etc.

### Lógica de negocio

#### Services:
Encapsula la lógica principal del negocio y de la aplicación

#### Helpers:
Los cuales nos van a proporcionar utilidades específicas para el negocio

### Estilos

#### Estilos (styles):
Contiene estilos CSS (globales) o CSS-in-JS

### TypeScript y configuraciones

#### Types:
para tipos, enumeraciones e interfaces generales de TypeScript

#### Configs:
Configuraciones para la aplicación (por ejemplo, variables de entorno)

#### Constantes (constants):
valores constantes, sin cambios (por ejemplo, export const MINUTES_PER_HOUR = 60)

### Comunicación con el Backend

#### api:
Para definir la lógica que se comunica con los servidores o nuestras API

#### graphql:
Donde definimos código específico de GraphQL

### Gestión de los Estados

#### states/store:
Donde definiremos la lógica de gestión de estados globales (podemos usar Zustand, Valtio, Jotai, etc.)

#### reducers, store, actions, selectors:
Para toda la lógica específica de Redux

### Enrutamiento

#### routes/router:
Definición de rutas (si estás usando React Router o similar).

#### pages:
Definición de componentes para las páginas de nuestro proyecto

### Testing
#### tests:
Pruebas unitarias y otros tipos de pruebas para el código

## Conclusiones

Cuando vamos a elegir una estructura de carpetas correcta para nuestros proyectos de React debe basarse en el tamaño y la complejidad del proyecto. Si bien la "Organización 1" puede ser suficiente para proyectos pequeños, los "Organización 2" y "Organización 3" ofrecen estructuras más organizadas y modulares para proyectos medianos y grandes. Personalmente, suelo recomendar la estructura de carpetas usando la "Organización 2". Además, es sumamente importante comprender que los nombres de carpetas comunes ayuda a mantener una arquitectura consistente e intuitiva en todas las aplicaciones React


