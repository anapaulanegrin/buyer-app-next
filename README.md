#  Buyer App - Groovy Music Store (Marketplace)

Este repositorio contiene el código fuente de la **Buyer App**, el módulo orientado al usuario final de un sistema integral de Marketplace (estilo Mercado Libre) basado en una arquitectura de microservicios. 

El proyecto fue desarrollado como parte de la cursada de **Ingeniería de Aplicaciones Web (1er Cuatrimestre 2026)** en la Universidad Nacional del Sur.

 **Deploy:** **[Buyer App - Groovy Music Store ](https://proyecto-c-buyer2-groovy-music-store.vercel.app/)**

##  Documentación General del Sistema

Dado que esta aplicación es una pieza dentro de un ecosistema distribuido, la planificación detallada del proyecto se encuentra en un repositorio compartido con todo el equipo. 

 **[Ver Documentación](https://github.com/IAW-2026/proyecto-c-etapa-1-groovy-music-store/tree/main#documentaci%C3%B3n)**

Allí se detallan:
* Descripción funcional y responsabilidades de cada módulo.
* Diseño y contratos de las APIs inter-servicios.
* Modelo de datos global.
* Estrategia de usuarios compartidos.

##  Mi Rol y Desarrollo

Fui la responsable del diseño, implementación y despliegue de extremo a extremo de esta **Buyer App**. Mi objetivo fue construir la interfaz para los compradores, manteniendo el aislamiento de la base de datos local y orquestando la comunicación con el resto de las aplicaciones del sistema:

*    **Catálogo de Productos:** Consumo de la API de la **Seller App** para la búsqueda de productos, gestión del carrito y validación de stock.
*    **Procesamiento de Pagos:** Integración con la **Payments App** para delegar el flujo de cobro utilizando Mercado Pago (sandbox).
*    **Seguimiento de Envíos:** Comunicación con la **Shipping App** para consultar el estado logístico y mostrar el historial de entregas.
*    **API RESTful Propia:** Diseño y exposición de endpoints dedicados (ej. `/api/orders/payment-status` y `/api/orders/shipping-status`) para recibir notificaciones y actualizaciones asíncronas desde los otros módulos, manteniendo sincronizada la base de datos local del comprador.
*    **Seguridad e Integración:** Implementación de validación de **tokens JWT** como método de autenticación general y centralizado para proteger el acceso a los endpoints de información sensible expuestos en el sistema.
  
##  Stack Tecnológico

*   **Framework:** Next.js 
*   **Estilos:** Tailwind CSS
*   **Base de Datos:** PostgreSQL (Neon)
*   **ORM:** Prisma
*   **Autenticación:** Clerk
*   **Despliegue:** Vercel
