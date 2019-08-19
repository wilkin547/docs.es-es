---
title: Cree servicios resistentes preparados para la nube. aceptación de errores transitorios en la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Cree servicios resistentes preparados para la nube. aceptación de errores transitorios en la nube
ms.date: 04/30/2018
ms.openlocfilehash: 5d25fb0d15ff7b9f04b9491454d1368e4aa7f593
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578358"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creación de servicios resistentes y aptos para la nube: aceptación de errores transitorios en la nube

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. No se trata de evitar los errores, sino de aceptar el hecho de que se produzcan errores y, a continuación, responder a ellos de forma que se evite el tiempo de inactividad o la pérdida de datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

La aplicación está lista para la nube cuando, como mínimo, implementa un modelo de resistencia basado en software, en lugar de un modelo basado en hardware. La aplicación en la nube debe adoptar los errores parciales que se producirán con certeza. Diseñar o refactorizar parcialmente la aplicación para lograr resistencia con errores parciales esperados. Debe diseñarse para que se corresponda con errores parciales, como interrupciones y nodos transitorios de red o máquinas virtuales que se bloquean en la nube. Incluso los contenedores que se mueven a otro nodo dentro de un clúster de Orchestrator pueden producir errores cortos intermitentes dentro de la aplicación.

## <a name="handling-partial-failure"></a>Controlar errores parciales

En una aplicación basada en la nube, existe un riesgo de que se produzca un error parcial. Por ejemplo, puede producirse un error en una única instancia de sitio web o en un contenedor, o puede que no esté disponible o no responda durante un breve período de tiempo. O bien, una sola máquina virtual o servidor podría bloquearse.

Dado que los clientes y los servicios son procesos independientes, es posible que un servicio no pueda responder de forma oportuna a la solicitud de un cliente. El servicio puede estar sobrecargado y responder lentamente a las solicitudes, o puede que no sea accesible durante un breve período de tiempo debido a problemas de red.

Por ejemplo, considere una aplicación .NET monolítica que tiene acceso a una base de datos de Azure SQL Database. Si la base de datos SQL de Azure o cualquier otro servicio de terceros no responden durante un breve período de tiempo (una base de datos SQL de Azure puede moverse a otro nodo o servidor y no responder durante unos segundos), cuando el usuario intenta realizar cualquier acción, la aplicación podría bloquearse y mostrarse w una excepción en el mismo momento.

Podría producirse un escenario similar en una aplicación que consuma servicios HTTP. Es posible que la red o el propio servicio no estén disponibles en la nube durante un breve error transitorio.

Una aplicación resistente como la que se muestra en la figura 4-9 debe implementar técnicas como "reintentos con retroceso exponencial" para ofrecer a la aplicación una oportunidad de controlar los errores transitorios en los recursos. También debe usar "disyuntores" en las aplicaciones. Un disyuntor impide que una aplicación intente obtener acceso a un recurso cuando realmente se trata de un error a largo plazo. Mediante el uso de un disyuntor, la aplicación evita la provocación de una denegación de servicio a sí misma.

![Errores parciales administrados por reintentos con retroceso exponencial](./media/image9.png)

> **Figura 4-9.** Errores parciales administrados por reintentos con retroceso exponencial

Puede usar estas técnicas tanto en recursos HTTP como en recursos de base de datos. En la figura 4-9, la aplicación se basa en una arquitectura de tres niveles, por lo que necesita estas técnicas en el nivel de servicios (HTTP) y en el nivel de capa de datos (TCP). En una aplicación monolítica que solo usa una capa de aplicación única, además de la base de datos (sin servicios o microservicios adicionales), es posible que el control de los errores transitorios en el nivel de conexión de base de datos sea suficiente. En ese escenario, solo se requiere una configuración concreta de la conexión de base de datos.

Al implementar comunicaciones resistentes que tienen acceso a la base de datos, en función de la versión de .NET que esté usando, puede ser sencillo (por ejemplo, [con Entity Framework 6 o posterior](/ef/ef6/fundamentals/connection-resiliency/retry-logic). Solo es cuestión de configurar la conexión de base de datos). O bien, puede que necesite usar bibliotecas adicionales como el [bloque de aplicaciones de control de errores transitorios](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (para versiones anteriores de .net) o incluso implementar su propia biblioteca.

Al implementar los reintentos HTTP y los disyuntores, la recomendación para .NET es usar la biblioteca [Polly](https://github.com/App-vNext/Polly) , que tiene como destino .NET Framework 4,0, .NET Framework 4,5 y .net Standard 1,1, que incluye compatibilidad con .net Core.

Para obtener información sobre cómo implementar estrategias para controlar errores parciales en la nube, consulte las referencias siguientes.

### <a name="additional-resources"></a>Recursos adicionales

- **Implementación de una comunicación resistente para controlar errores parciales**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework resistencia de conexión y lógica de reintento (versión 6 y posteriores)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Bloque de aplicaciones de control de errores transitorios**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Biblioteca Polly para la comunicación HTTP resistente**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Siguiente](modernize-your-apps-with-monitoring-and-telemetry.md)
