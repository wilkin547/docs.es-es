---
title: Presentación de la aplicación de referencia eShopOnContainers
description: Introducción a la aplicación de referencia de microservicios nativos en la nube de eShopOnContainers para ASP.NET Core y Azure.
ms.date: 01/19/2021
ms.openlocfilehash: 35aa92794d8488c3de60f42af52654c4c26aad82
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505679"
---
# <a name="introducing-eshoponcontainers-reference-app"></a>Presentación de la aplicación de referencia eShopOnContainers

Microsoft, en colaboración con los principales expertos de la comunidad, ha creado una aplicación de referencia de microservicios nativa en la nube, eShopOnContainers. Esta aplicación se ha creado para exhibir con .NET y Docker, y opcionalmente Azure, Kubernetes y Visual Studio, para crear un escaparate en línea.

![Captura de pantalla de la aplicación de ejemplo eShopOnContainers.](./media/eshoponcontainers-sample-app-screenshot.png)

**Figura 2-1**. Captura de pantalla de la aplicación de ejemplo eShopOnContainers.

Antes de comenzar este capítulo, se recomienda descargar la [aplicación de referencia eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers). Si lo hace, debe ser más fácil de seguir junto con la información que se presenta.

## <a name="features-and-requirements"></a>Características y requisitos

Comencemos con una revisión de las características y los requisitos de la aplicación. La aplicación eShopOnContainers representa una tienda en línea que vende varios productos físicos, como camisetas y tazas de café. Si ha comprado cualquier cosa en línea antes, la experiencia del uso del almacén debe ser relativamente familiar. Estas son algunas de las características básicas que implementa el almacén:

- Enumeración de elementos del catálogo
- Filtrar elementos por tipo
- Filtrar elementos por marca
- Agregar elementos a la cesta de la compra
- Editar o quitar elementos de la cesta
- Restauración
- Registrar una cuenta
- Iniciar sesión
- Cerrar sesión
- Revisar pedidos

La aplicación también tiene los siguientes requisitos no funcionales:

- Debe ser de alta disponibilidad y debe escalarse automáticamente para satisfacer el mayor tráfico (y reducirse verticalmente una vez que el tráfico se encuentre).
- Debe proporcionar una supervisión fácil de usar de los registros de estado y diagnóstico para ayudar a solucionar los problemas que encuentre.
- Debe admitir un proceso de desarrollo ágil, incluida la compatibilidad con la integración e implementación continuas (CI/CD).
- Además de los dos servidores front-end web (aplicación tradicional y de página única), la aplicación también debe admitir aplicaciones cliente móviles que ejecuten diferentes tipos de sistemas operativos.
- Debe admitir el hospedaje multiplataforma y el desarrollo multiplataforma.

![arquitectura de desarrollo de aplicaciones de referencia de eShopOnContainers.](./media/eshoponcontainers-development-architecture.png)

**Figura 2-2**. arquitectura de desarrollo de aplicaciones de referencia de eShopOnContainers.

Se puede acceder a la aplicación eShopOnContainers desde clientes Web o móviles que tienen acceso a la aplicación a través de HTTPS que tienen como destino la aplicación de servidor de ASP.NET Core MVC o una puerta de enlace de API adecuada. Las puertas de enlace de API ofrecen varias ventajas, como separar los servicios back-end de clientes front-end individuales y proporcionar una mejor seguridad. La aplicación también usa un patrón relacionado conocido como back-ends-para-frontends (BFF), que recomienda crear puertas de enlace de API independientes para cada cliente front-end. La arquitectura de referencia muestra la división de las puertas de enlace de API en función de si la solicitud procede de un cliente web o móvil.

La funcionalidad de la aplicación se divide en muchos microservicios distintos. Hay servicios responsables de la autenticación y la identidad, la enumeración de elementos del catálogo de productos, la administración de las cestas de la compra de los usuarios y la realización de pedidos. Cada uno de estos servicios independientes tiene su propio almacenamiento persistente. No hay un almacén de datos maestros único con el que interactúen todos los servicios. En su lugar, la coordinación y la comunicación entre los servicios se realizan según sea necesario y mediante un bus de mensajes.

Cada uno de los microservicios diferentes está diseñado de manera diferente, en función de sus requisitos individuales. Este aspecto significa que su pila de tecnología puede ser diferente, aunque todos se han creado con .NET y están diseñados para la nube. Los servicios más sencillos proporcionan acceso básico de creación-lectura-actualización-eliminación (CRUD) a los almacenes de datos subyacentes, mientras que los servicios más avanzados usan métodos de diseño de Domain-Driven y patrones para administrar la complejidad empresarial.

![Distintos tipos de microservicios](./media/different-kinds-of-microservices.png)

**Figura 2-3**. Distintos tipos de microservicios.

## <a name="overview-of-the-code"></a>Información general sobre el código

Dado que usa microservicios, la aplicación eShopOnContainers incluye bastantes proyectos y soluciones en su repositorio de GitHub. Además de separar soluciones y archivos ejecutables, los distintos servicios están diseñados para ejecutarse dentro de sus propios contenedores, durante el desarrollo local y en tiempo de ejecución en producción. En la figura 2-4 se muestra la solución completa de Visual Studio, en la que se organizan los distintos proyectos.

![Proyectos de la solución de Visual Studio.](./media/projects-in-visual-studio-solution.png)

**Figura 2-4**. Proyectos de la solución de Visual Studio.

El código está organizado para admitir los diferentes microservicios y, dentro de cada microservicio, el código se divide en la lógica de dominio, los problemas de infraestructura y el punto de conexión de servicio o interfaz de usuario. En muchos casos, los servicios de Azure pueden satisfacer las dependencias de cada servicio en producción y opciones alternativas para el desarrollo local. Vamos a examinar cómo se asignan los requisitos de la aplicación a los servicios de Azure.

## <a name="understanding-microservices"></a>Descripción de los microservicios

Este libro se centra en las aplicaciones nativas en la nube creadas con la tecnología de Azure. Para obtener más información sobre los procedimientos recomendados para los microservicios y cómo diseñar aplicaciones basadas en microservicios, lea el libro complementario, [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

>[!div class="step-by-step"]
>[Anterior](candidate-apps.md)
>[Siguiente](map-eshoponcontainers-azure-services.md)
