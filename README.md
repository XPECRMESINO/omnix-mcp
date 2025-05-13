
# 📖 Índice

## Propuesta tools/res como dependencias y manejo de repo

- [🧩 Estructura de MCP Tools](#-estructura-de-mcp-tools)
- [Opción 1: Repositorio Único (Monorepo)](#opción-1-repositorio-único-monorepo)
  - [📊 Diagrama Mermaid (Opción 1):](#-diagrama-mermaid-opción-1)
- [Opción 2: Repositorios Independientes (Multirepo)](#opción-2-repositorios-independientes-multirepo)
  - [📌 Posible approach:](#-posible-approach)

## Propuesta de buenas prácticas

- [📖 1. Entender y Documentar el Caso de Uso](#-1-entender-y-documentar-el-caso-de-uso)
  - [🔹 Propósito Claro y Definido](#-propósito-claro-y-definido)
  - [🔹 Requerimientos Claros y Definidos](#-requerimientos-claros-y-definidos)
- [🔧 2. Requerimientos del MCP](#-2-requerimientos-del-mcp)
  - [🔹 Herramientas para acciones](#-herramientas-para-acciones)
  - [🔹 Recursos para operaciones de sólo lectura](#-recursos-para-operaciones-de-sólo-lectura)
- [🏷️ 3. Nombres Intuitivos y Claros](#-3-nombres-intuitivos-y-claros)
  - [🔹 Nombres descriptivos para herramientas](#-nombres-descriptivos-para-herramientas)
  - [🔹 Seguir Naming Conventions](#-seguir-naming-conventions)
- [📐 4. Definición Clara y Precisa de Esquemas I/O](#-4-definición-clara-y-precisa-de-esquemas-io)
  - [🔹 Marcar requeridos en los schemas](#-marcar-requeridos-en-los-schemas)
  - [🔹 Simplificación de los schemas](#-simplificación-de-los-schemas)
  - [🔹 Simplificar datos externos](#-simplificar-datos-externos)
- [📦 5. Uso de SDK Oficiales y Actualizados](#-5-uso-de-sdk-oficiales-y-actualizados)
- [🔐 6. Almacenamiento Seguro (Secure Vaults)](#-6-almacenamiento-seguro-secure-vaults)
- [🔑 7. Autenticación con Sistemas Externos](#-7-autenticación-con-sistemas-externos)
- [🚨 8. Manejo de Errores y Excepciones](#-8-manejo-de-errores-y-excepciones)
  - [🔹 Mensajes de error claros para AI](#-mensajes-de-error-claros-para-ai)
  - [🔹 Mapeo de errores externos](#-mapeo-de-errores-externos)
  - [🔹 Estrategias de Retries](#-estrategias-de-retries)
- [🚀 9. Rendimiento y Optimización](#-9-rendimiento-y-optimización)
  - [🔹 Uso de cachés](#-uso-de-cachés)
  - [🔹 Límites de APIs externas](#-límites-de-apis-externas)
  - [🔹 Procesos Asíncronos](#-procesos-asíncronos)
- [📋 10. Gestión y Estructura de Logs](#-10-gestión-y-estructura-de-logs)
- [🚀 11. Stack Tecnológico](#-11-stack-tecnológico)
- [🛡️ 12. Pruebas de Lógica y Seguridad](#-11-pruebas-de-lógica-y-seguridad)
- [📚 13. Documentación Detallada de las Herramientas (Tools)](#-12-documentación-detallada-de-las-herramientas-tools)
  - [🔧 Herramienta: obtener_estado_pedido](#-herramienta-obtener_estado_pedido)
- [🚧 14. Pasos de Instalación y Uso del MCP Server](#-13-pasos-de-instalación-y-uso-del-mcp-server)


# 🛠️ Guía de Buenas Prácticas para Implementación de MCP Servers - Omnix IA

Este documento establece los lineamientos claros para implementar MCP Servers de forma efectiva, segura y eficiente en Omnix IA.

---

## 📖 1. Entender y Documentar el Caso de Uso

### 🔹 Propósito Claro y Definido
- Define claramente el objetivo del MCP Server.
- Describe qué problemática específica resolverá.
- Detalla cómo este servidor mejorará la eficiencia o desempeño del agente AI.

### 🔹 Requerimientos Claros y Definidos
- Especifica detalladamente todos los requerimientos técnicos y funcionales del servidor.
- Incluye dependencias con otros sistemas o herramientas.

---

## 🔧 2. Requerimientos del MCP

### 🔹 Herramientas para acciones
- Proporciona y documenta claramente las herramientas o APIs externas necesarias para que el agente pueda ejecutar acciones.

### 🔹 Recursos para operaciones de sólo lectura
- Define claramente cuáles recursos estarán disponibles exclusivamente para operaciones de consulta o lectura.

---

## 🏷️ 3. Nombres Intuitivos y Claros

### 🔹 Nombres descriptivos para herramientas
- Cada herramienta o acción debe tener un nombre claro y significativo (como si estuviese orientado a una persona).

### 🔹 Seguir Naming Conventions
- Acordar y documentar una convención de nombres estándar.
- **Nota**: Brandon definirá y proporcionará las convenciones específicas de nomenclatura para herramientas y acciones.

---

## 📐 4. Definición Clara y Precisa de Esquemas I/O

### 🔹 Marcar requeridos en los schemas
- Documenta explícitamente en los schemas JSON cuáles campos son obligatorios y cuáles opcionales.

### 🔹 Simplificación de los schemas
- Mantén los esquemas simplificados para reducir el consumo de tokens en interacciones con la IA.
- Evita estructuras complejas o anidadas innecesarias.

### 🔹 Simplificar datos externos
- Transforma o simplifica datos complejos provenientes de sistemas externos antes de presentarlos al agente AI.
- No siempre es necesario que los datos sean transparentes (ByPass); adapta los esquemas según la necesidad del caso de uso.

---

## 📦 5. Uso de SDK Oficiales y Actualizados
- Asegúrate de utilizar siempre SDK oficiales proporcionados por proveedores externos.
- Mantén las bibliotecas y herramientas siempre actualizadas a la última versión estable.

---

## 🔐 6. Almacenamiento Seguro (Secure Vaults)
- Utiliza gestores de secretos seguros (ej. AWS Secrets Manager, Azure Key Vault, HashiCorp Vault).
- Nunca guardes credenciales o información sensible en código o repositorios públicos.

---

## 🔑 7. Autenticación con Sistemas Externos
- El MCP Server gestionará internamente la autenticación y actualización de tokens con sistemas externos.
- Automatiza completamente la gestión del ciclo de vida de tokens.

---

## 🚨 8. Manejo de Errores y Excepciones

### 🔹 Mensajes de error claros para AI
- Define mensajes de error entendibles por el agente AI.
- Evita mensajes técnicos o códigos crípticos.

### 🔹 Mapeo de errores externos
- Mapea claramente errores provenientes de servicios externos a errores internos en el contexto de la solución MCP.

### 🔹 Estrategias de Retries
- Implementa reintentos automáticos con políticas claras y configurables para mejorar resiliencia.

---

## 🚀 9. Rendimiento y Optimización

### 🔹 Uso de cachés
- Usa cachés internos o externos (Redis, Memcached) para reducir latencia y mejorar rendimiento.

### 🔹 Límites de APIs externas
- Documenta claramente límites y restricciones de las APIs externas para evitar sobrepasarlos.

### 🔹 Procesos Asíncronos
- Utiliza procesamiento asíncrono siempre que sea posible para optimizar tiempos de respuesta.

---

## 📋 10. Gestión y Estructura de Logs
- Define una estructura estándar y clara para todos los logs generados.
- Los logs deben permitir una fácil identificación y seguimiento de problemas.

Ejemplo sugerido:

```json
{
    "timestamp": "2025-05-12T10:35:21Z",
    "level": "INFO",
    "service": "MCP-Server",
    "operation": "fetch_user_data",
    "message": "Successfully retrieved user data",
    "userId": "12345",
    "transactionId": "67890"
}
```
## 🚀 11. Stack Tecnológico

A continuación, se describe el stack tecnológico base recomendado para el desarrollo de MCP Tools y MCP Servers.

🔹 **TypeScript**

  Lenguaje Principal: TypeScript será el lenguaje de programación estándar.
  Razón: Su sistema de tipado estático ayuda a detectar errores en tiempo de desarrollo, mejora la legibilidad y mantenibilidad del código, y ofrece un excelente autocompletado y refactorización en los IDEs modernos. Esto es crucial para construir sistemas robustos y colaborativos.

🔹 **Zod** para Schemas

  Declaración y Validación de Esquemas: Se utilizará Zod (https://www.npmjs.com/package/zod) para definir y validar los esquemas de entrada/salida (I/O Schemas) de las herramientas.
  Razón: Zod es una biblioteca de validación "TypeScript-first" que permite inferir tipos estáticos de TypeScript directamente desde las definiciones de los esquemas de validación. Esto asegura que los datos en tiempo de ejecución coincidan con las estructuras de tipos definidas, reduciendo la posibilidad de errores de datos y facilitando la integración entre el MCP Server y los agentes AI. Además, sus mensajes de error son detallados y fáciles de usar.

🔹 **MCP Inspector** para Pruebas

  Pruebas de Herramientas MCP: Se utilizará @modelcontextprotocol/inspector (https://www.npmjs.com/package/@modelcontextprotocol/inspector) para realizar pruebas funcionales y de conformidad de las MCP Tools.
  Razón: Esta herramienta está específicamente diseñada para el Protocolo de Contexto de Modelo (MCP). Permite validar que las herramientas cumplan con las especificaciones del protocolo, verificar los esquemas de entrada/salida, y asegurar que la lógica de la herramienta funcione como se espera antes de su integración en un MCP Server.

🔹 **Configuración de tsconfig.json**

  Se recomienda la siguiente configuración base para tsconfig.json para proyectos de MCP Server/Tool:
  JSON
  ```json
    {
      "compilerOptions": {
        "target": "ES2022", // Compila a una versión moderna de JavaScript, compatible con versiones recientes de Node.js.
        "module": "NodeNext", // Utiliza el sistema de módulos más reciente de Node.js (ESM).
        "moduleResolution": "NodeNext", // Resuelve módulos al estilo de Node.js para ESM.
        "baseUrl": "./src", // Directorio base para resolver rutas no relativas.
        "paths": { // Define alias para rutas, facilitando importaciones.
          "@/*": ["*"]
        },
        "outDir": "./dist", // Directorio de salida para los archivos compilados.
        "rootDir": "./src", // Especifica el directorio raíz de los archivos fuente.
        "esModuleInterop": true, // Permite la interoperabilidad con módulos CommonJS.
        "forceConsistentCasingInFileNames": true, // Asegura la consistencia en el uso de mayúsculas/minúsculas en los nombres de archivo.
        "strict": true, // Habilita todas las opciones de chequeo de tipos estrictos (noImplicitAny, strictNullChecks, etc.).
        "noImplicitAny": true, // Exige tipos explícitos para variables y parámetros donde el tipo no puede ser inferido.
        "strictNullChecks": true, // Manejo explícito de `null` y `undefined`.
        "skipLibCheck": true, // Omite la verificación de tipos de los archivos de declaración (.d.ts) de las dependencias. Acelera la compilación.
        "resolveJsonModule": true, // Permite importar archivos .json como módulos.
        "declaration": true, // Genera archivos de declaración .d.ts para los módulos TypeScript.
        "sourceMap": true, // Genera sourcemaps para facilitar el debugging.
        "experimentalDecorators": true, // Habilita el uso de decoradores (útil para algunos frameworks o librerías).
        "emitDecoratorMetadata": true // Emite metadatos de tipo para decoradores (usado por librerías como TypeORM, InversifyJS).
      },
      "include": ["src/**/*.ts"], // Patrones para incluir archivos en la compilación.
      "exclude": ["node_modules", "dist", "**/*.test.ts", "**/*.spec.ts"] // Patrones para excluir archivos de la compilación.
    }
  ```

🔹 Otros Aspectos Técnicos Clave
  - Linting y Formateo:
    - **ESLint y Prettier**: Es crucial configurar ESLint para el análisis estático del código y Prettier para el formateo automático. Esto asegura un estilo de código consistente en todo el proyecto y ayuda a prevenir errores comunes.
    Razón: Mantienen la calidad y legibilidad del código, facilitan la colaboración y reducen el tiempo dedicado a discusiones sobre estilo.
  
  #### TODO
  - Estructura de carpetas
  - esquema de pruebas unitarias

## 🛡️ 12. Pruebas de Lógica y Seguridad
- Implementa pruebas automatizadas que cubran lógica de negocio y validación de seguridad.
- Realiza regularmente escaneos de seguridad y auditorías internas del código.

## 📚 13. Documentación Detallada de las Herramientas (Tools)
Cada herramienta debe contar con documentación específica que contenga:

- Propósito claro: ¿Para qué sirve la herramienta?
- Ejemplos prácticos de uso: cómo y cuándo utilizar la herramienta.
- Esquema de entrada (Input Schema): documentado explícitamente en JSON.
- Esquema de salida (Output Schema): documentado explícitamente en JSON.

Ejemplo de documentación básica para una herramienta:

### 🔧 Herramienta: obtener_estado_pedido

#### Propósito:
Consultar el estado actual de un pedido en la plataforma de e-commerce.

#### Ejemplo de uso:
```json
{
  "order_id": "ABC1234"
}
```

Input Schema:
```json
{
  "type": "object",
  "properties": {
    "order_id": {"type": "string"}
  },
  "required": ["order_id"]
}
```

Output Schema:
```json
{
  "type": "object",
  "properties": {
    "status": {"type": "string"},
    "estimated_delivery": {"type": "string", "format": "date-time"},
    "tracking_link": {"type": "string"}
  },
  "required": ["status"]
}
```


---

## 🚧 14. Pasos de Instalación y Uso del MCP Server

Documenta claramente:

- Requisitos previos de software y hardware.
- Procedimientos paso a paso para la instalación.
- Configuración inicial y parámetros obligatorios.
- Instrucciones detalladas para despliegue y ejecución en producción.
- Comandos básicos para monitoreo y mantenimiento.


# 📐 Implementación de MCP Tools como Dependencias

La idea principal es mantener cada MCP Tool o recurso independiente y modular, para que puedan ser reutilizados y fácilmente añadidos como dependencias a diferentes proyectos MCP Server, siempre y cuando estos sirvan de uso general. Por ejemplo, las tools de get-order, get-sg, get-item-info, get-route, etc.. Se creen como tools generales que puedan ser usadas en cualquier proyuecto MCP server donde se necesite usar sin necesidad de crear tools repetidas por cada proyecto MCP, sería algo así como tener tools generales y tools de específicas por proyecto MCP.

Beneficios:

- Mayor modularidad y reutilización.
- Menor acoplamiento.
- Fácil actualización y mantenimiento individual.
- Escalabilidad y flexibilidad en el desarrollo.

## 🧩 Estructura de MCP Tools

Cada MCP Tool o recurso debe tener la siguiente estructura base:

- Tipo: Indica si es una herramienta (tool) o un recurso (resource).
- Nombre: Claro e intuitivo.
- I/O Schema: JSON schemas claramente definidos.
- Función (Tool) o Ubicación (Resource): El módulo expone claramente la función (si es Tool) o la ubicación del recurso (si es Resource).

📊 Diagrama Mermaid (Implementación propuesta):

```mermaid
flowchart LR
    subgraph Tools_Repo [Tools Repo]
        T1[Gral Tool 1]
        T2[Gral Tool 2]
        T3[Gral Tool 3]
    end

    T1 -->|As Dependency| MCP[MCP Server Project #1]
    T2 -->|As Dependency| MCP
    T3 -->|As Dependency| MCP

    MCP --> |Custom impl.|ST1[Specific Tool 1]
    MCP --> |Custom impl.|ST2[Specific Tool 2]
    MCP --> |Custom impl.|ST3[Specific Tool 3]

    classDef dashed stroke-dasharray: 5 5;
    class ST1,ST2,ST3 dashed;
```

# 📁 2. Gestión de MCP Tools en Repositorios

Se presentan dos opciones de organización para manejar MCP tools dentro del control de versiones (git).

## Opción 1: Repositorio Único (Monorepo)

Descripción: Todas las herramientas en un único repositorio (omnix-mcp-modules), organizadas en carpetas.

Ventajas:
- Fácil acceso y visibilidad global.
- Menos overhead administrativo (permisos, accesos, CI/CD).
- Fácil reutilización interna.

Desventajas:
- Mayor tamaño del repositorio.
- Posible dependencia entre herramientas si no se gestionan bien.
- Riesgo de conflictos frecuentes.

### 📊 Diagrama Mermaid (Opción 1):

```mermaid
graph TD
    Repo["omnix-mcp-modules"] --> tool_mod_1[tool-mod-1]
    Repo --> tool_mod_2[tool-mod-2]
    Repo --> tool_mod_3[tool-mod-3]

    classDef box fill:#bbf,stroke:#333,stroke-width:1px
    class Repo box
```

## Opción 2: Repositorios Independientes (Multirepo)

Descripción: Cada herramienta tiene su propio repositorio independiente (tool-mod-1, tool-mod-2, tool-mod-3).

Ventajas:
- Claridad y modularidad extremas.
- Mayor facilidad para mantener y actualizar individualmente.
- Reducción de conflictos entre herramientas.

Desventajas:
- Mayor complejidad administrativa (múltiples pipelines CI/CD, accesos, permisos).
- Posible dificultad para descubrir herramientas existentes.

```mermaid
graph TD
    repo1["Repo: tool-mod-1"]
    repo2["Repo: tool-mod-2"]
    repo3["Repo: tool-mod-3"]

    classDef box fill:#bfb,stroke:#333,stroke-width:1px
    class repo1,repo2,repo3 box
```

### 📌 Posible approach:

Podríamos iniciar con monorepo y evaluar migración futura a multirepo según necesidades y si crecen tanto las tools que se hace necesario.