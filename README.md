# 🌍 WIPS: Web Interactiva Para Sismos

## 📋 Descripción del Proyecto

**WIPS** es una plataforma web interactiva diseñada para el monitoreo en tiempo real de actividad sísmica. El proyecto integra datos sísmicos actualizados con un sistema de notificaciones instantáneas para mejorar la gestión de información sísmica a través del sistema UGS (Unidad de Gestión Sísmica).

## 🎯 Objetivo Principal

Desarrollar una web interactiva sobre sismos con datos en tiempo real para mejorar el sistema de UGS, proporcionando a los usuarios una herramienta efectiva para:

- Monitorear actividad sísmica en tiempo real
- Recibir notificaciones de nuevos registros sísmicos
- Visualizar datos sísmicos en mapas interactivos
- Analizar magnitud y profundidad de sismos
- Acceder a información histórica de eventos sísmicos

## ⚡ Características Principales

### 1. **Monitoreo en Tiempo Real**
- Datos sísmicos actualizados constantemente
- Visualización de últimos registros
- Información detallada de cada evento

### 2. **Sistema de Notificaciones**
- Alertas configurables por magnitud mínima
- Notificaciones instantáneas de nuevos registros
- Historial de notificaciones recientes

### 3. **Mapas Interactivos**
- Visualización geográfica de epicentros
- Información de ubicación y profundidad
- Análisis espacial de eventos

### 4. **Análisis de Datos**
- Estadísticas de magnitud y profundidad
- Tendencias de actividad sísmica
- Comparativas históricas

## 👥 Equipo de Desarrollo

| Nombre | Rol | Responsabilidades |
|--------|-----|-------------------|
| **Sofía López** | Desarrolladora Frontend | Interfaz de usuario, componentes React, diseño responsivo |
| **Mateo Lastra** | Desarrollador Backend | APIs, base de datos, lógica de negocio |
| **Juan Manuel Londoño** | Desarrollador Full Stack | Integración completa, DevOps, despliegue |

## 📚 Información Académica

- **Asignatura:** Lenguajes de Programación y POO
- **Modalidad:** Prototipo / Proyecto
- **Año:** 2025
- **Institución:** [Tu Institución]

## 🛠️ Stack Tecnológico

### Frontend
- **React 19** - Framework de interfaz de usuario
- **TypeScript** - Tipado estático
- **Tailwind CSS** - Estilos y diseño responsivo
- **shadcn/ui** - Componentes de interfaz
- **Wouter** - Enrutamiento
- **Lucide React** - Iconografía

### Backend
- **Express 4** - Servidor web
- **tRPC 11** - RPC type-safe
- **Drizzle ORM** - Gestión de base de datos
- **MySQL** - Base de datos relacional
- **Node.js** - Runtime de JavaScript

### Herramientas de Desarrollo
- **Vite** - Build tool moderno
- **Vitest** - Framework de testing
- **Prettier** - Formateo de código
- **TypeScript** - Verificación de tipos

## 📁 Estructura del Proyecto

```
wips_website/
├── client/                 # Código frontend
│   ├── src/
│   │   ├── pages/         # Páginas (Home, Dashboard)
│   │   ├── components/    # Componentes reutilizables
│   │   ├── hooks/         # Custom hooks
│   │   └── lib/           # Utilidades
│   └── public/            # Archivos estáticos
├── server/                # Código backend
│   ├── routers.ts         # Definición de APIs
│   ├── db.ts              # Funciones de base de datos
│   └── seismicService.ts  # Servicio de datos sísmicos
├── drizzle/               # Esquema y migraciones
├── dist/                  # Archivos compilados
└── package.json           # Dependencias
```

## 🚀 Instalación y Uso

### Requisitos Previos

- Node.js 20 o superior
- pnpm (gestor de paquetes)
- MySQL 8.0 o superior

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/tu-usuario/wips_website.git
cd wips_website
```

2. **Instalar dependencias**
```bash
pnpm install
```

3. **Configurar variables de entorno**
```bash
# Crear archivo .env
cp .env.example .env

# Editar .env con tus valores
DATABASE_URL=mysql://usuario:contraseña@localhost:3306/wips
JWT_SECRET=tu_secreto_seguro
VITE_APP_ID=tu_app_id
# ... más variables (ver ENV_SETUP.md)
```

4. **Aplicar migraciones de base de datos**
```bash
pnpm db:push
```

5. **Iniciar en desarrollo**
```bash
pnpm dev
```

6. **Acceder a la aplicación**
```
http://localhost:3000
```

## 📦 Scripts Disponibles

```bash
# Desarrollo con hot reload
pnpm dev

# Compilar para producción
pnpm build

# Ejecutar servidor compilado
pnpm start

# Verificar tipos TypeScript
pnpm check

# Formatear código
pnpm format

# Ejecutar tests
pnpm test

# Aplicar migraciones de BD
pnpm db:push
```

## 🌐 Despliegue

### Netlify (Recomendado)

1. Conecta tu repositorio a Netlify
2. Configura variables de entorno
3. Netlify detectará automáticamente la configuración
4. Deploy automático en cada push

Ver `NETLIFY_DEPLOYMENT.md` para instrucciones detalladas.

### Vercel

```bash
vercel --prod
```

### Docker

```bash
docker build -t wips .
docker run -p 3000:3000 --env-file .env wips
```

## 📊 Base de Datos

### Tablas Principales

**users** - Usuarios registrados
- id (PK)
- name, email
- loginMethod, role
- createdAt, lastSignedIn

**seismic_records** - Registros sísmicos
- id (PK)
- magnitude, latitude, longitude, depth
- location, timestamp, source
- createdAt

**notification_subscriptions** - Suscripciones
- id (PK)
- userId (FK)
- minMagnitude, isActive
- createdAt

## 🔌 API Endpoints

### Datos Sísmicos
- `GET /api/trpc/seismic.latest` - Últimos registros
- `GET /api/trpc/seismic.byMagnitude` - Filtrar por magnitud

### Notificaciones
- `POST /api/trpc/notifications.subscribe` - Suscribirse
- `GET /api/trpc/notifications.getSubscription` - Obtener suscripción

### Autenticación
- `GET /api/trpc/auth.me` - Usuario actual
- `POST /api/trpc/auth.logout` - Cerrar sesión

## 🔐 Seguridad

- Autenticación OAuth integrada
- Tokens JWT para sesiones
- Contraseñas hasheadas
- Variables de entorno para credenciales
- HTTPS en producción
- CORS configurado

## 🧪 Testing

```bash
# Ejecutar tests
pnpm test

# Tests con coverage
pnpm test:coverage

# Tests en modo watch
pnpm test:watch
```

## 📖 Documentación Adicional

- **README_DEPLOYMENT.md** - Guía rápida de despliegue
- **DEPLOYMENT.md** - Guía detallada de despliegue
- **ENV_SETUP.md** - Configuración de variables de entorno
- **ESTRUCTURA_PROYECTO.md** - Estructura completa del proyecto
- **NETLIFY_DEPLOYMENT.md** - Guía específica para Netlify

## 🐛 Solución de Problemas

### Error: "Cannot find module"
```bash
rm -rf node_modules pnpm-lock.yaml
pnpm install
```

### Error: "Database connection failed"
- Verifica que MySQL está ejecutándose
- Comprueba que DATABASE_URL es correcto
- Ejecuta `pnpm db:push` para crear tablas

### Error 404 en Netlify
- Verifica que `netlify.toml` está en la raíz
- Comprueba que `_redirects` existe
- Redeploy desde Netlify

### Puerto 3000 en uso
```bash
PORT=3001 pnpm start
```

## 📝 Contribuciones

Este es un proyecto académico. Para contribuciones:

1. Fork el repositorio
2. Crea una rama para tu feature
3. Commit tus cambios
4. Push a la rama
5. Abre un Pull Request

## 📄 Licencia

MIT License - 2025 WIPS Project

## 📞 Contacto y Soporte

Para preguntas o problemas:

- **Sofía López** - Frontend: sofia.lopez@email.com
- **Mateo Lastra** - Backend: mateo.lastra@email.com
- **Juan Manuel Londoño** - Full Stack: juan.londono@email.com

## 🙏 Agradecimientos

- Lenguajes de Programación y POO - Asignatura
- [Institución] - Por el apoyo académico
- Comunidad de código abierto - Por las herramientas utilizadas

## 📈 Roadmap Futuro

- [ ] Integración con API de USGS
- [ ] Predicción de sismos con ML
- [ ] Aplicación móvil
- [ ] Análisis avanzado de datos
- [ ] Exportación de reportes
- [ ] Integración con sistemas de alerta
- [ ] Dashboard administrativo
- [ ] Análisis de patrones sísmicos

## 🔄 Historial de Versiones

### v1.0.0 (2025-10-20)
- Lanzamiento inicial
- Monitoreo en tiempo real
- Sistema de notificaciones
- Autenticación OAuth
- Dashboard interactivo

---

**Última actualización:** 20 de octubre de 2025

**Estado:** En desarrollo activo

**Versión:** 1.0.0

