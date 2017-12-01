---
title: "Crear la interfaz de usuario compuesta en función de microservicios, incluidos visual forma de interfaz de usuario y el diseño generado por varios microservicios"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Crear la interfaz de usuario compuesta en función de microservicios, incluidos visual forma de interfaz de usuario y el diseño generado por varios microservicios"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4b32fed5eb0de02b01665efa4368eb83e3fda08d
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2017
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Crear la interfaz de usuario compuesta en función de microservicios, incluidos visual forma de interfaz de usuario y el diseño generado por varios microservicios

Arquitectura de Microservicios a menudo comienza por el lado del servidor datos y la lógica de control. Sin embargo, un enfoque más avanzado consiste en diseñar la aplicación en la que interfaz de usuario en función de microservicios también. Esto significa que tiene una interfaz de usuario compuesta generada por el microservicios, en lugar de tener microservicios en el servidor y solo una aplicación de cliente monolítico consumiendo el microservicios. Con este enfoque, el microservicios que compilar pueden ser completo con lógica y representación visual.

Figura 4-20 muestra el método más sencillo de consumo solo microservicios desde una aplicación cliente monolítico. Por supuesto, podría tener un servicio de ASP.NET MVC entre generar el código HTML y JavaScript. En la ilustración es una simplificación que resalta los que tienen un solo cliente (monolítico) consumiendo el microservicios, que solo se centran en la lógica y los datos y no en la forma de interfaz de usuario (HTML y JavaScript) de la interfaz de usuario.

![](./media/image20.png)

**Figura 4-20**. Una aplicación de interfaz de usuario monolítica consumiendo microservicios de back-end

En cambio, una interfaz de usuario compuesta con precisión generan y compuesta por el microservicios por sí mismos. Algunos de los microservicios controlan la forma visual de áreas específicas de la interfaz de usuario. La principal diferencia es que tiene componentes de interfaz de usuario de cliente (por ejemplo, clases de TS) basados en plantillas y el modelo de vista de la IU modelado de datos para esas plantillas procede cada microservicio.

En tiempo de inicio de aplicación de cliente, cada uno de los componentes de interfaz de usuario de cliente (por ejemplo, clases de TypeScript) registra automáticamente con un microservicio infraestructura capaz de proporcionar ViewModels para un escenario determinado. Si el microservicio cambia la forma, también cambia la interfaz de usuario.

Figura 4-21 muestra una versión de este enfoque de interfaz de usuario compuesta. Esto se ha simplificado, ya que es posible que tenga otros microservicios que se agregan granular elementos basados en técnicas diferentes, depende de si está creando un enfoque de web tradicionales (MVC de ASP.NET) o un SPA (aplicación de página única).

![](./media/image21.png)

**Figura 4-21**. Ejemplo de una aplicación de interfaz de usuario compuesta formada por microservicios de back-end

Cada una de esas microservicios de composición de la interfaz de usuario sería similar a una puerta de enlace de API pequeño. Pero en este caso cada uno de ellos es el responsable de un área pequeña de la interfaz de usuario.

Un enfoque de interfaz de usuario compuesto que está controlado por microservicios puede ser más difícil o menos por lo tanto, dependiendo de qué tecnologías de interfaz de usuario que esté utilizando. Por ejemplo, no los utilizará las mismas técnicas para la creación de una aplicación web tradicional que se use para generar un SPA o aplicación móvil nativo (como al desarrollar aplicaciones de Xamarin, que pueden ser más difícil de este enfoque).

El [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) aplicación de ejemplo utiliza el método de interfaz de usuario monolítico por distintos motivos. En primer lugar, es una introducción a microservicios y contenedores. Una interfaz de usuario compuesto es más avanzado, pero también requiere un mayor complejidad al diseño y desarrollo de la interfaz de usuario. En segundo lugar, eShopOnContainers también proporciona una aplicación nativa móvil en función de Xamarin, que le resulte más compleja en el cliente C\# lado.

Sin embargo, le recomendamos que utilice las siguientes referencias para obtener más información sobre compuesto de que interfaz de usuario en función de microservicios.

## <a name="additional-resources"></a>Recursos adicionales

-   **Interfaz de usuario compuesta mediante ASP.NET (del determinado taller)**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. El front-end monolítico en la arquitectura de Microservicios**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti. El secreto de la composición de interfaz de usuario mejor**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic. Componentes Web front-end se incluyen en Microservicios**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Administración de front-end de la arquitectura de Microservicios**\
    [*http://Allegro.Tech/2016/03/Managing-Frontend-in-the-microservices-Architecture.HTML*](http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Anterior] (microservicios-direccionabilidad-servicio-registry.md) [siguiente] (resistente-alta-disponibilidad-microservices.md)
