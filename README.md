# Guía de Implementación y Uso del Sistema GENIA

## Introducción

Este documento proporciona una guía completa para la implementación, configuración y uso del sistema GENIA, una plataforma SaaS con inteligencia artificial que automatiza contenido, embudos, campañas y tareas para negocios digitales.

## Componentes del Sistema

El sistema GENIA está compuesto por los siguientes componentes principales:

1. **Frontend**: Interfaz de usuario desarrollada con React y Tailwind CSS, desplegada en Vercel.
2. **Backend**: API desarrollada con FastAPI, desplegada en Render.
3. **Base de Datos**: Alojada en Supabase, con tablas para usuarios, créditos, acciones y referidos.
4. **Pagos**: Integración con Stripe para gestionar suscripciones y pagos.
5. **Automatizaciones**: Flujos de trabajo configurados en Make para onboarding, referidos, etc.
6. **Clones de IA**: Implementados con OpenAI GPT-4 para diferentes funcionalidades.

## Requisitos Previos

Para implementar y utilizar el sistema GENIA, necesitas:

- Cuenta en Vercel para el frontend
- Cuenta en Render para el backend
- Cuenta en Supabase para la base de datos
- Cuenta en Stripe para pagos
- Cuenta en Make para automatizaciones
- Cuenta en OpenAI para los clones de IA

## Implementación del Sistema

### 1. Configuración de Supabase

1. Accede a tu cuenta de Supabase (https://app.supabase.io/)
2. Crea un nuevo proyecto o utiliza uno existente
3. Ejecuta el script SQL proporcionado en `supabase_tables.sql` para crear las tablas necesarias
4. Guarda la URL del proyecto y las claves API (anon/public y service_role)

### 2. Configuración de Stripe

1. Accede a tu cuenta de Stripe (https://dashboard.stripe.com/)
2. Crea los siguientes planes de suscripción:
   - GENIA Free: Plan gratuito
   - GENIA Starter: Plan de prueba de 7 días ($9.99/semana)
   - GENIA Pro: Plan profesional ($29.99/mes)
   - GENIA Elite: Plan elite ($99.99/mes)
3. Guarda las claves API (pública y secreta)

### 3. Configuración de Make

1. Accede a tu cuenta de Make (https://www.make.com/)
2. Importa los flujos proporcionados en la carpeta `make_templates`
3. Configura los webhooks para cada flujo
4. Conecta Make con Supabase utilizando las credenciales guardadas
5. Guarda las URLs de los webhooks generados

### 4. Despliegue del Backend

1. Accede a tu cuenta de Render (https://render.com/)
2. Crea un nuevo servicio web
3. Conecta con el repositorio o sube los archivos de la carpeta `backend`
4. Configura las variables de entorno según el archivo `.env.example`
5. Despliega el servicio y guarda la URL generada

### 5. Despliegue del Frontend

1. Accede a tu cuenta de Vercel (https://vercel.com/)
2. Crea un nuevo proyecto
3. Conecta con el repositorio o sube los archivos de la carpeta `frontend`
4. Configura las variables de entorno según el archivo `.env.example`
5. Despliega el proyecto y guarda la URL generada

### 6. Activación de Clones de IA

Los clones de IA se activan automáticamente cuando un usuario se registra en el sistema. No se requiere configuración adicional si ya has configurado correctamente las variables de entorno con tu API key de OpenAI.

## Uso del Sistema

### Acceso al Sistema

- **URL del Frontend**: https://genia-platform.vercel.app
- **URL del Backend**: https://genia-api.onrender.com

### Registro de Usuarios

1. Los usuarios pueden registrarse a través del formulario en la página de inicio
2. Al registrarse, se crea automáticamente una cuenta con plan Free
3. Se envía un correo de bienvenida con un enlace al panel personalizado

### Panel de Usuario

El panel de usuario incluye:

- Dashboard con estadísticas
- Acceso a los clones de IA según el plan
- Gestión de perfil y suscripción
- Visualización de créditos y referidos

### Clones de IA Disponibles

- **GENIA CEO**: Disponible en todos los planes
- **GENIA Funnel**: Disponible en planes Pro y Elite
- **GENIA Content**: Disponible en plan Elite
- **GENIA Bot**: Disponible en plan Elite

## Mantenimiento y Soporte

### Monitoreo del Sistema

- Verifica regularmente los logs en Vercel y Render
- Monitorea los flujos en Make para asegurarte de que se ejecutan correctamente
- Revisa periódicamente la base de datos en Supabase

### Actualizaciones

Para actualizar el sistema:

1. Modifica los archivos necesarios en las carpetas `frontend` o `backend`
2. Ejecuta el script `deploy.py` para desplegar los cambios
3. Verifica que todo funcione correctamente con el script `test_functionality.py`

### Solución de Problemas

Si encuentras problemas:

1. Revisa los logs en Vercel, Render, Supabase y Make
2. Verifica que todas las integraciones estén funcionando correctamente
3. Ejecuta el script `test_functionality.py` para identificar posibles fallos

## Archivos Incluidos

- `frontend/`: Código fuente del frontend
- `backend/`: Código fuente del backend
- `clones/`: Configuración de los clones de IA
- `make_templates/`: Plantillas para los flujos de Make
- `supabase_tables.sql`: Script SQL para crear las tablas en Supabase
- `deploy.py`: Script para desplegar el sistema completo
- `test_functionality.py`: Script para probar la funcionalidad integrada
- `deployment_summary.json`: Resumen del despliegue

## Contacto y Soporte

Para cualquier consulta o soporte adicional, contacta a:

- Email: soporte@genia.ai
- Sitio web: https://genia.ai/soporte

---

© 2025 GENIA. Todos los derechos reservados.
