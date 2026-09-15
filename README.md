# Hostal Diamante

Sistema de gestión para un hostal con foco en operaciones diarias, control de habitaciones, reservas, estadías, clientes y reportes financieros. Este proyecto está pensado para administrar un negocio de alojamiento de forma centralizada y eficiente, reduciendo la fricción operativa entre recepción, administración y seguimiento de clientes.

## Visión general

Hostal Diamante es una aplicación web de gestión hotelera diseñada para controlar todo el ciclo operativo de un hostal: desde la reserva hasta la salida del huésped, pasando por el manejo de clientes, pagos, disponibilidad de habitaciones y reportes del negocio.

El sistema está desarrollado como una solución moderna para uso interno, orientada a operadores, administradores y personal del hotel que necesitan consultar información en tiempo real y tomar decisiones rápidas.

## ¿De qué trata este proyecto?

La aplicación centraliza las tareas clave de un establecimiento de alojamiento:

- Gestión de habitaciones y su estado operativo
- Registro y control de reservas
- Administración de estadías activas y cerradas
- Registro de clientes y países de origen
- Control de pagos y movimientos de caja
- Seguimiento de empresas asociadas o clientes corporativos
- Reportes diarios y análisis operativos
- Seguridad de acceso con autenticación para personal

Además, incorpora lógica de negocio aplicada a la operación real de un hostal, como:

- habitaciones con tipos y estado (libre, ocupada, reservada, deshabilitada)
- registro de clientes con documentos y datos de contacto
- seguimiento de clientes baneados o inactivos
- asociación de huéspedes con estadías y pagos
- gestión de reservas vinculadas a habitaciones específicas
- control de salidas, costos y cierre de estadía

## Características destacadas

### Operación hotelera realista

El proyecto refleja un flujo real de trabajo de un hostal, no una maqueta conceptual. Está pensado para cubrir tareas operativas concretas y repetitivas del día a día.

### Panel administrativo centralizado

La aplicación organiza la gestión en módulos claros:

- habitaciones
- reservas
- estadías
- clientes
- empresas
- reportes
- usuarios y autenticación

### Control de datos y consistencia

El modelo de datos está estructurado para mantener relaciones entre clientes, habitaciones, reservas y pagos, con validaciones en el backend y una base de datos relacional.

### Escalabilidad de negocio

La arquitectura permite seguir extendiendo funcionalidades como reportes más avanzados, analíticas, exportación, roles permisivos, auditoría de cambios y automatización de procesos.

### Enfoque en experiencia operativa

La interfaz está pensada para ser ágil y funcional para personal que trabaja con mucha información en tiempo real, con tablas, filtros, formularios y estados visuales claros.

## Stack tecnológico

### Frontend

- Next.js 16
- React 19
- TypeScript
- Tailwind CSS
- React Icons
- Zustand para manejo de estado local
- Zod para validación de datos

### Backend y lógica de negocio

- Next.js App Router
- Prisma ORM
- PostgreSQL
- Better Auth para autenticación y sesiones
- Docker Compose para entorno de base de datos

### Infraestructura y entorno

- Node.js
- pnpm
- PostgreSQL 17
- Prisma migrations para evolución del esquema

## Arquitectura y modelo de datos

El proyecto utiliza una base de datos relacional con PostgreSQL, modelando entidades clave como:

- User
- Session
- Account
- Verification
- Room
- Stay
- Reservation
- Client
- Country
- ClientCompany
- Pay
- RoomActive
- DayComment

Esto permite un control más robusto de la información que maneja el hostal, evitando lógica dispersa y favoreciendo la integridad de los datos.

## Estructura principal del proyecto

```bash
src/
├── app/                 # rutas y páginas de la aplicación
├── components/          # componentes reutilizables por módulo
├── generated/           # cliente Prisma generado
├── lib/                 # utilidades, autenticación y configuración
├── store/               # estado global / Zustand
public/                  # assets estáticos
prisma/                  # esquema ORM y migraciones
postgres/                # datos locales de PostgreSQL
```

## Módulos funcionales

### 1. Habitaciones

Administración de cuartos, tipos, precios, estado actual y disponibilidad. También incluye control de activación/desactivación y visualización del mapa de habitaciones.

### 2. Reservas

Registro de reservas con nombre, personas, fecha, contacto, monto y asignación de habitación. Se gestionan reservas activas y no activas.

### 3. Estadías

Se manejan los ingresos de huéspedes, fechas, motivo de visita, origen, pagos, costos, comentarios y cierre de estadías.

### 4. Clientes

Registro de clientes con tipo de documento, nacionalidad, datos personales, comentarios, historial y estado de bloqueo.

### 5. Empresas / clientes corporativos

Gestión de empresas asociadas con tarifas, lista de chasis y documentación adicional vinculada a estadías.

### 6. Pagos

Control de ingresos y salidas relacionadas con la operación del alojamiento, con tipos de pago y registros detallados.

### 7. Reportes

Módulos para análisis de información diaria y reportes de operación del negocio.

## Calidad del proyecto

Este proyecto demuestra varias cualidades valiosas para un perfil de desarrollo full-stack:

- dominio de aplicaciones reales con lógica de negocio no trivial
- manejo de relaciones complejas en base de datos
- uso de arquitectura moderna con Next.js App Router
- implementación de autenticación segura con sesiones
- validación y estructura de datos con TypeScript + Zod
- diseño de interfaces funcionales para entornos productivos
- capacidad para trabajar con flujo de trabajo real de gestión empresarial
- foco en mantenibilidad y modularidad del código

## Requisitos para ejecutar el proyecto

### Prerquisitos

- Node.js 20+
- pnpm
- Docker

### Instalación

```bash
pnpm install
```

### Levantar base de datos

```bash
docker-compose up -d
```

### Generar cliente Prisma

```bash
npx prisma generate
```

### Ejecutar en desarrollo

```bash
pnpm dev
```

### Compilar para producción

```bash
pnpm build
```

## Estado del proyecto

El proyecto está estructurado como una solución funcional de gestión hotelera con enfoque productivo, pensada para ser usada por un equipo operativo y ampliada con nuevas funcionalidades según el crecimiento del negocio.

## Conclusión

Hostal Diamante refleja un trabajo orientado a la resolución de problemas reales del sector hostelero: automatización de procesos, control operativo, gestión de clientes y reportes eficientes. Es un proyecto relevante para mostrar experiencia en full-stack, desarrollo de sistemas de administración, modelado de datos complejos y diseño de interfaces de negocio.

---

Desarrollado con enfoque en productividad, organización operativa y experiencia de usuario para entornos empresariales de alojamiento.
