---
title: Crear servicios resistentes listos para la nube. Adoptar errores transitorios en la nube
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Crear servicios resistentes listos para la nube. Adoptar errores transitorios en la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aaf1ef968600a56d91267c6c12efa90d99446dd7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Crear servicios resistentes listos para la nube: adoptar errores transitorios en la nube 

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. Resistencia no es cuestión de evitar errores, pero acepta el hecho de que se producirán errores y, a continuación, responder a ellas de forma que se evita perder el tiempo de inactividad o datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

La aplicación está lista para la nube cuando, como mínimo, implementa un modelo basado en software de resistencia, en lugar de un modelo basado en hardware. La aplicación en la nube debe adoptar los errores parciales que por supuesto, se producirán. Debe diseñar o parcialmente refactorizar la aplicación si desea conseguir resistencia a errores parciales esperados. Se deben diseñar para hacer frente a errores parciales, como las interrupciones de red transitorios y nodos o de bloqueo en la nube. Incluso los contenedores que se mueven a otro nodo en un clúster de orchestrator pueden provocar errores cortos intermitentes dentro de la aplicación.

## <a name="handling-partial-failure"></a>Control de errores parciales

En una aplicación basada en la nube, hay un riesgo de error parcial omnipresente. Por ejemplo, podría producirse un error en una instancia de un sitio Web único o un contenedor o podría ser no está disponible o no responde durante poco tiempo. O bien, puede bloquearse una única máquina virtual o servidor.

Dado que los clientes y servicios son procesos independientes, es posible que un servicio no pueda responder de manera oportuna a solicitud del cliente. El servicio podría estar sobrecargado y muy lentamente responder a las solicitudes, o puede que simplemente no sea accesible durante un breve tiempo debido a problemas de red.

Por ejemplo, imagine una aplicación de .NET monolítica que tiene acceso a una base de datos en la base de datos de SQL Azure. Si la base de datos de SQL Azure o cualquier otro servicio de terceros no responde durante un breve tiempo (una base de datos de SQL Azure se pueden mover a un servidor o de otro nodo y dejar de responder durante unos segundos), cuando el usuario intenta realizar ninguna acción, la aplicación puede bloquearse y mostrar w una excepción en el mismo momento.

Una situación similar puede producirse en una aplicación que consuma servicios HTTP. La red o el propio servicio no estén disponible en la nube durante un error transitorio, corto.

Una aplicación resistente como se muestra en la figura 4-9 debe implementar técnicas como "reintentos con retroceso exponencial" para dar una oportunidad para controlar errores transitorios en recursos de la aplicación. También debe utilizar "los disyuntores" en sus aplicaciones. Un disyuntor detiene una aplicación intente tener acceso a un recurso cuando es realmente un error de larga duración. Mediante el uso de un disyuntor, la aplicación evita provocar una denegación de servicio a sí mismo.

![Errores parciales controladas reintentos con retroceso exponencial](./media/image9.png)

> **Figura 4-9.** Errores parciales controladas reintentos con retroceso exponencial

Puede utilizar estas técnicas en recursos HTTP y en los recursos de base de datos. En la figura 4-9, la aplicación se basa en una arquitectura de 3 niveles, por lo que necesita estas técnicas en el nivel de servicios (HTTP) y en el nivel de capa de datos (TCP). En una aplicación monolítica que usa una capa de aplicación único además de la base de datos (no hay servicios adicionales o microservicios), control de errores transitorios en el nivel de conexión de base de datos puede ser suficiente. En ese caso, se requiere normalmente solo una configuración específica de la conexión de base de datos.

Al implementar las comunicaciones resistentes que tienen acceso a la base de datos, según la versión de .NET que usa, puede ser muy sencilla (por ejemplo, [con Entity Framework 6 o posterior](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), es simplemente una cuestión de configurar la conexión de base de datos). O bien, tendrá que utilizar bibliotecas adicionales como la [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (para versiones anteriores de. NET), o incluso implementar su propia biblioteca.

Al implementar los reintentos HTTP y los disyuntores, la recomendación para .NET es usar el [Polly](https://github.com/App-vNext/Polly) biblioteca, que tiene como destino .NET 4.0, .NET 4.5 y .NET 1.1 estándar, que incluye compatibilidad con .NET Core.

Para obtener información sobre cómo implementar estrategias para controlar los errores parciales en la nube, consulte las siguientes referencias.

### <a name="additional-resources"></a>Recursos adicionales

-   **Implementación de la comunicación resistente para controlar los errores parciales**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies)

-   **Entity Framework conexión resistencia lógica de reintento y (versión 6 y versiones posterior)**

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   **El bloque de aplicaciones de control de errores transitorios**

<!-- -->

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   **Biblioteca de Polly para la comunicación HTTP resistente**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Siguiente](modernize-your-apps-with-monitoring-and-telemetry.md)
