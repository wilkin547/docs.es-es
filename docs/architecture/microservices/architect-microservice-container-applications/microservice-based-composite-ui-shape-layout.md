---
title: Creación de interfaces de usuario compuestas basadas en microservicios
description: La arquitectura de microservicios no es solo para el back-end. Obtenga una vista de inspección usándola en el front-end.
ms.date: 09/20/2018
ms.openlocfilehash: 0d1825d6183b79a0e10f70fc6cfee6ca79a837d8
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817832"
---
# <a name="creating-composite-ui-based-on-microservices"></a>Creación de interfaces de usuario compuestas basadas en microservicios

A menudo, la arquitectura de microservicios se inicia con el control de los datos y la lógica en el servidor. Sin embargo, un enfoque más avanzado consiste en diseñar la interfaz de usuario de la aplicación también en función de los microservicios. Esto significa tener una interfaz de usuario compuesta generada por los microservicios, en lugar de tener microservicios en el servidor y simplemente una aplicación cliente monolítica que consume los microservicios. Con este enfoque, los microservicios que crea pueden completarse con representación lógica y visual.

En la figura 4-20 se muestra el enfoque más sencillo que consiste en simplemente consumir microservicios desde una aplicación cliente monolítica. Por supuesto, también podría tener un servicio de ASP.NET MVC que produzca HTML y JavaScript. La figura es una simplificación que resalta que tiene una sola (monolítica) interfaz de usuario cliente que consume los microservicios, que solo se centran en la lógica y los datos y no en la forma de la interfaz de usuario (HTML y JavaScript).

![Aplicación monolítica de interfaz de usuario que se conecta a microservicios individuales.](./media/image20.png)

**Figura 4-20**. Una aplicación de interfaz de usuario monolítica que consume microservicios de back-end

En contraste, los propios microservicios generan y componen con precisión una interfaz de usuario compuesta. Algunos de los microservicios controlan la forma visual de áreas específicas de la interfaz de usuario. La principal diferencia es que tiene componentes de la interfaz de usuario cliente (por ejemplo, clases de TypeScript) basados en plantillas, y el ViewModel de la interfaz de usuario que perfila los datos para esas plantillas procede de cada microservicio.

En el momento de iniciarse la aplicación cliente, cada uno de los componentes de la interfaz de usuario cliente (por ejemplo, las clases de TypeScript) se registra con un microservicio de infraestructura capaz de proporcionar ViewModels para un escenario determinado. Si el microservicio cambia la forma, la interfaz de usuario también cambia.

En la figura 4-21 se muestra una versión de este enfoque de interfaz de usuario compuesta. Esto se simplifica porque es posible que tenga otros microservicios que agreguen elementos pormenorizados basados en otras técnicas. Depende de si va a crear un enfoque web tradicional (ASP.NET MVC) o una SPA (aplicación de página única).

![En la aplicación de interfaz de usuario compuesta, cada sección de la interfaz de usuario se genera mediante un microservicio de composición de interfaz de usuario, que actúa como una minipuerta de enlace.](./media/image21.png)

**Figura 4-21**. Ejemplo de una aplicación de interfaz de usuario compuesta formada por microservicios de back-end

Cada uno de esos microservicios de composición de interfaz de usuario sería similar a una puerta de enlace de API pequeña. Pero en este caso, cada uno es responsable de una pequeña área de la interfaz de usuario.

Un enfoque de interfaz de usuario compuesta controlada por microservicios puede ser más o menos complicado, según las tecnologías de interfaz de usuario que se usen. Por ejemplo, no usará las mismas técnicas para crear una aplicación web tradicional que para crear una SPA o una aplicación móvil nativa (como al desarrollar aplicaciones de Xamarin, que puede ser más complicado para este enfoque).

La aplicación de ejemplo [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) usa el enfoque de interfaz de usuario monolítica por distintos motivos. En primer lugar, es una introducción a los microservicios y los contenedores. Una interfaz de usuario compuesta es más avanzada, pero también necesita mayor complejidad al diseñar y desarrollar la interfaz de usuario. En segundo lugar, eShopOnContainers también proporciona una aplicación móvil nativa basada en Xamarin, lo que resultaría más complejo en el lado del cliente C\#.

Le recomendamos que use las siguientes referencias para saber más información sobre la interfaz de usuario compuesta basada en microservicios.

## <a name="additional-resources"></a>Recursos adicionales

- **Composición de la interfaz de usuario con ASP.NET (taller de Particular)**  \
  <https://github.com/Particular/Workshop/tree/master/demos/asp-net-core>

- **Ruben Oostinga. El front-end monolítico en la arquitectura de microservicios** \
  <https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/>

- **Mauro Servienti. El secreto de una mejor composición de la interfaz de usuario** \
  <https://particular.net/blog/secret-of-better-ui-composition>

- **Viktor Farcic. Inclusión de componentes web de front-end en los microservicios** \
  <https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/>

- **Administración de front-end en la arquitectura de microservicios** \
  <https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html>

>[!div class="step-by-step"]
>[Anterior](microservices-addressability-service-registry.md)
>[Siguiente](resilient-high-availability-microservices.md)
