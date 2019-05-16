---
title: Crear servicios resistentes listos para la nube. aceptación de errores transitorios en la nube
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Crear servicios resistentes listos para la nube. aceptación de errores transitorios en la nube
ms.date: 04/30/2018
ms.openlocfilehash: ca5d5e0c3af772ac52a02894c96889c776cf7d48
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643737"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creación de servicios resistentes y aptos para la nube: aceptación de errores transitorios en la nube

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. La resistencia no es sobre cómo evitar los errores, pero acepta el hecho de que se producirán errores y, a continuación, responder a ellas de forma que evite la pérdida de datos o el tiempo de inactividad. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

La aplicación está lista para la nube cuando, como mínimo, implementa un modelo basado en software de resistencia, en lugar de un modelo basado en hardware. La aplicación en la nube debe adoptar los errores parciales que seguramente se. Diseñar o parcialmente refactorizar la aplicación para lograr resistencia esperado errores parciales. Se deben diseñarse para hacer frente a errores parciales, como las interrupciones de red transitorios y nodos o máquinas virtuales que se bloquea en la nube. Incluso los contenedores que se mueven a otro nodo dentro de un clúster de orquestador pueden causar breves errores intermitentes dentro de la aplicación.

## <a name="handling-partial-failure"></a>Controlar errores parciales

En una aplicación basada en la nube, hay un riesgo siempre presente de error parcial. Por ejemplo, podría producir un error en una instancia de un sitio Web único o un contenedor, o podría ser no está disponible o no responde durante un breve período. O bien, un único servidor o máquina virtual puede bloquearse.

Dado que los clientes y servicios son procesos independientes, un servicio no pueda responder de manera oportuna a petición de un cliente. El servicio podría estar sobrecargado y respuesta lenta a las solicitudes, o podría no ser accesible durante un breve tiempo debido a problemas de red.

Por ejemplo, considere la posibilidad de una aplicación monolítica de .NET que tiene acceso a una base de datos en Azure SQL Database. Si la base de datos SQL de Azure o cualquier otro servicio de terceros no responde para una breve tiempo (Azure SQL database se puede mover a un nodo diferente o un servidor y dejar de responder durante unos segundos), cuando el usuario intenta llevar a cabo cualquier acción, la aplicación puede bloquearse y mostrar w una excepción en el mismo momento.

Una situación similar puede producirse en una aplicación que consume los servicios HTTP. La red o el propio servicio no esté disponible en la nube durante un error transitorio, corto.

Una aplicación resistente como el que se muestra en la figura 4-9 debe implementar técnicas, como "reintentos con retroceso exponencial" para dar una oportunidad para controlar errores transitorios en los recursos de la aplicación. También debe usar "disyuntores" en sus aplicaciones. Un disyuntor se detiene una aplicación intente tener acceso a un recurso cuando es realmente un error de larga duración. Mediante el uso de un disyuntor, la aplicación evita que invitan reflexión una denegación de servicio a sí mismo.

![Errores parciales controladas los reintentos con retroceso exponencial](./media/image9.png)

> **Figura 4-9.** Errores parciales controladas los reintentos con retroceso exponencial

Puede utilizar estas técnicas en los recursos HTTP y en los recursos de base de datos. En la figura 4-9, la aplicación se basa en una arquitectura de 3 niveles, por lo que necesita estas técnicas en el nivel de servicios (HTTP) y en el nivel de datos (TCP). En una aplicación monolítica que se usa sólo un nivel de aplicación único además de la base de datos (sin servicios adicionales ni microservicios), control de errores transitorios en el nivel de conexión de base de datos podría ser suficiente. En ese caso, se requiere solo una configuración específica de la conexión de base de datos.

Al implementar communications resistente que tienen acceso a la base de datos, según la versión de .NET que usa, puede ser sencillo (por ejemplo, [con Entity Framework 6 o posterior](/ef/ef6/fundamentals/connection-resiliency/retry-logic). (Es simplemente una cuestión de configurar la conexión de base de datos). O bien, es posible que deba utilizar bibliotecas adicionales, como el [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (para versiones anteriores de. NET), o incluso implementar su propia biblioteca.

Al implementar los reintentos de HTTP y los disyuntores, la recomendación para .NET es usar el [Polly](https://github.com/App-vNext/Polly) biblioteca, que tiene como destino .NET Framework 4.0, .NET Framework 4.5 y .NET Standard 1.1, que incluye compatibilidad con .NET Core.

Para obtener información sobre cómo implementar estrategias para tratar errores parciales en la nube, consulte las siguientes referencias.

### <a name="additional-resources"></a>Recursos adicionales

- **Implementación de la comunicación resistente para controlar errores parciales**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework reintento y resistencia lógica de conexión (versión 6 y versiones posterior)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **El bloque de aplicaciones de control de errores transitorios**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Biblioteca de Polly para la comunicación HTTP resistente**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Siguiente](modernize-your-apps-with-monitoring-and-telemetry.md)
