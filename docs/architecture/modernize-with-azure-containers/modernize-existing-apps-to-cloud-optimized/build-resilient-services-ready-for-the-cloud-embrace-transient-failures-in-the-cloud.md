---
title: 'Creación de servicios resistentes y aptos para la nube: aceptación de errores transitorios en la nube'
description: 'Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Creación de servicios resistentes y aptos para la nube: aceptación de errores transitorios en la nube'
ms.date: 12/21/2020
ms.openlocfilehash: 4d592a5761cdf696f3e57516d747cbd770512053
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025334"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Creación de servicios resistentes y aptos para la nube: aceptación de errores transitorios en la nube

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. La resistencia no es evitar los errores, sino aceptar el hecho de que se producirán errores y responder a ellos para evitar el tiempo de inactividad o la pérdida de datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

La aplicación está lista para la nube cuando, como mínimo, implementa un modelo de resistencia basado en software, en lugar de un modelo basado en hardware. La aplicación en la nube debe adoptar los errores parciales que se producirán con certeza. Diseñe o refactorice parcialmente la aplicación para lograr resistencia a los errores parciales esperados. Debe estar diseñada para hacer frente a errores parciales, como las interrupciones de red transitorias o el bloqueo de nodos o máquinas virtuales en la nube. Incluso los contenedores que se trasladan a otro nodo dentro de un clúster de orquestador pueden causar breves errores intermitentes dentro de la aplicación.

## <a name="handling-partial-failure"></a>Controlar errores parciales

En una aplicación basada en la nube, siempre hay un riesgo de que se produzca un error parcial. Por ejemplo, puede producirse un error en una única instancia de un sitio web o contenedor, o puede que no esté disponible o no responda durante un breve período de tiempo. O bien, podría bloquearse una sola máquina virtual o servidor.

Como los clientes y los servicios son procesos independientes, es posible que un servicio no pueda responder de forma oportuna a una solicitud del cliente. Es posible que el servicio esté sobrecargado y responda lentamente a las solicitudes, o bien que no sea accesible durante un breve período debido a problemas de red.

Por ejemplo, considere una aplicación de .NET monolítica que tiene acceso a una base de datos de Azure SQL Database. Si la base de datos de Azure SQL o cualquier otro servicio de terceros no responden durante un breve período de tiempo (una base de datos de Azure SQL podría haberse movido a otro nodo o servidor y no responder durante unos segundos), cuando el usuario intenta realizar cualquier acción, la aplicación podría bloquearse y mostrarse una excepción al momento.

Podría producirse un escenario similar en una aplicación que consume servicios HTTP. Es posible que la red o el propio servicio no estén disponibles en la nube durante un breve error transitorio.

Una aplicación resistente como la que se muestra en la figura 4-9 debe implementar técnicas como "reintentos con retroceso exponencial" para ofrecer a la aplicación la posibilidad de controlar los errores transitorios en los recursos. También debe usar "disyuntores" en las aplicaciones. Un disyuntor impide que una aplicación intente obtener acceso a un recurso cuando realmente se trata de un error a largo plazo. Los disyuntores evitan que la aplicación se provoque una denegación del servicio a sí misma.

![Diagrama de errores parciales administrados por reintentos con retroceso exponencial.](./media/retry-partial-failures.png)

**Figura 4-9.** Errores parciales administrados por reintentos con retroceso exponencial

Puede usar estas técnicas tanto en recursos HTTP como en recursos de base de datos. En la figura 4-9, la aplicación se basa en una arquitectura de tres niveles, por lo que necesita estas técnicas en el nivel de servicios (HTTP) y en el nivel de capa de datos (TCP). En una aplicación monolítica que usa un único nivel de aplicación, además de la base de datos (sin servicios o microservicios adicionales), es posible que el control de los errores transitorios en el nivel de conexión de base de datos sea suficiente. En ese escenario, solo se requiere una configuración concreta de la conexión de base de datos.

Implementar comunicaciones resistentes que tienen acceso a la base de datos, en función de la versión de .NET que use, puede ser sencillo (por ejemplo, con [Entity Framework 6 o versiones posteriores](/ef/ef6/fundamentals/connection-resiliency/retry-logic). Solo es cuestión de configurar la conexión de base de datos). O bien, puede que necesite usar bibliotecas adicionales como [Transient Fault Handling Application Block](/previous-versions/msp-n-p/hh680934(v=pandp.50)) (para versiones anteriores de .NET) o incluso implementar su propia biblioteca.

Al implementar los reintentos HTTP y los disyuntores, la recomendación para .NET consiste en usar la biblioteca [Polly](https://github.com/App-vNext/Polly), que tiene como destino .NET Standard 1.1 (cobertura: .NET Core 1.0, Mono, Xamarin, UWP, y WP8.1 y versiones posteriores), y .NET Standard 2.0 y versiones posteriores (cobertura: .NET Core 2.0 y versiones posteriores, .NET Core 3.0, y destinos posteriores de Mono, Xamarin y UWP). El paquete NuGet también incluye destinos directos para .NET Framework 4.6.1 y 4.7.2.

Para obtener información sobre cómo implementar estrategias para controlar errores parciales en la nube, consulte las referencias siguientes.

### <a name="additional-resources"></a>Recursos adicionales

- **Implementación de una comunicación resistente para controlar errores parciales**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Resistencia de la conexión de Entity Framework y lógica de reintento (versión 6 y posteriores)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Bloque de aplicación de control de errores transitorios**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Biblioteca Polly para una comunicación HTTP resistente**

    <https://github.com/App-vNext/Polly>

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Siguiente](modernize-your-apps-with-monitoring-and-telemetry.md)
