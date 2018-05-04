---
title: Crear una interfaz de usuario compuesta en función de los microservicios, incluidos la forma y el diseño visual de la interfaz de usuario generados por varios microservicios
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Crear una interfaz de usuario compuesta en función de los microservicios, incluidos la forma y el diseño visual de la interfaz de usuario generados por varios microservicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 55b643fa6f87e5e2b1f49ba201032df655195b46
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Crear una interfaz de usuario compuesta en función de los microservicios, incluidos la forma y el diseño visual de la interfaz de usuario generados por varios microservicios

A menudo, la arquitectura de microservicios se inicia con el lado servidor controlando los datos y la lógica. Sin embargo, un enfoque más avanzado consiste en diseñar la interfaz de usuario de la aplicación también en función de los microservicios. Esto significa tener una interfaz de usuario compuesta generada por los microservicios, en lugar de tener microservicios en el servidor y simplemente una aplicación cliente monolítica que consume los microservicios. Con este enfoque, los microservicios que crea pueden completarse con representación lógica y visual.

En la figura 4-20 se muestra el enfoque más sencillo que consiste en simplemente consumir microservicios desde una aplicación cliente monolítica. Por supuesto, también podría tener un servicio de ASP.NET MVC que produzca HTML y JavaScript. La figura es una simplificación que resalta que tiene una sola (monolítica) interfaz de usuario cliente que consume los microservicios, que solo se centran en la lógica y los datos y no en la forma de la interfaz de usuario (HTML y JavaScript).

![](./media/image20.png)

**Figura 4-20**. Una aplicación de interfaz de usuario monolítica que consume microservicios de back-end

En contraste, los propios microservicios generan y componen con precisión una interfaz de usuario compuesta. Algunos de los microservicios controlan la forma visual de áreas específicas de la interfaz de usuario. La principal diferencia es que tiene componentes de la interfaz de usuario cliente (por ejemplo, clases de TS) basados en plantillas, y el ViewModel de la interfaz de usuario que perfila los datos para esas plantillas procede de cada microservicio.

En el momento de iniciarse la aplicación cliente, cada uno de los componentes de la interfaz de usuario cliente (por ejemplo, las clases de TypeScript) se registra con un microservicio de infraestructura capaz de proporcionar ViewModels para un escenario determinado. Si el microservicio cambia la forma, la interfaz de usuario también cambia.

En la figura 4-21 se muestra una versión de este enfoque de interfaz de usuario compuesta. Esto se ha simplificado, ya que es posible que tenga otros microservicios que agregan elementos granulares basados en técnicas diferentes, en función de si está creando un enfoque web tradicional (ASP.NET MVC) o una SPA (aplicación de página única).

![](./media/image21.png)

**Figura 4-21**. Ejemplo de una aplicación de interfaz de usuario compuesta formada por microservicios de back-end

Cada uno de esos microservicios de composición de interfaz de usuario sería similar a una puerta de enlace de API pequeña. Pero en este caso, cada uno de ellos es responsable de un área pequeña de la interfaz de usuario.

Un enfoque de interfaz de usuario compuesta controlada por microservicios puede ser más o menos complicado, según las tecnologías de interfaz de usuario que esté usando. Por ejemplo, no usará las mismas técnicas para crear una aplicación web tradicional que para crear una SPA o una aplicación móvil nativa (como al desarrollar aplicaciones de Xamarin, que puede ser más complicado para este enfoque).

La aplicación de ejemplo [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) usa el enfoque de interfaz de usuario monolítica por distintos motivos. En primer lugar, es una introducción a los microservicios y los contenedores. Una interfaz de usuario compuesta es más avanzada, pero también necesita mayor complejidad al diseñar y desarrollar la interfaz de usuario. En segundo lugar, eShopOnContainers también proporciona una aplicación móvil nativa basada en Xamarin, lo que resultaría más complejo en el lado del cliente C\#.

Le recomendamos que use las siguientes referencias para saber más información sobre la interfaz de usuario compuesta basada en microservicios.

## <a name="additional-resources"></a>Recursos adicionales

-   **Composite UI using ASP.NET (Particular’s Workshop) [Composición de interfaz de usuario con ASP.NET (taller de Particular)]**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture (Front-end monolítico en la arquitectura de microservicios)**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti. The secret of better UI composition (El secreto de una mejor composición de la interfaz de usuario)**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic. Including Front-End Web Components Into Microservices (Inclusión de componentes web de front-end en los microservicios)**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Managing Frontend in the Microservices Architecture (Administración de front-end en la arquitectura de microservicios)**\
    [*https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Previous] (microservices-addressability-service-registry.md) [Next] (resilient-high-availability-microservices.md)
