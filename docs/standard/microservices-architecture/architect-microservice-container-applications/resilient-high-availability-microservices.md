---
title: Resistencia y la alta disponibilidad en microservicios
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Resistencia y la alta disponibilidad en microservicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 149e28ac7bd7383e4e960ed8a226943e2b9bdaa1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resistencia y la alta disponibilidad en microservicios

Tratar errores inesperados es uno de los problemas más difíciles de resolver, especialmente en un sistema distribuido. Gran parte del código que los desarrolladores escribir implica el control de excepciones, y también es donde se dedica más tiempo en las pruebas. El problema es más complejo que escribir código para controlar los errores. ¿Qué ocurre cuando se produce un error en el equipo donde se ejecuta el microservicio? No solo es necesario detectar este error de microservicio (un problema de disco duro en su propio), pero también necesita algo que reinicie su microservicio.

Un microservicio necesita sea resistente a errores y para que pueda reiniciar a menudo en otro equipo para la disponibilidad. Esta resistencia también consiste en tomar el estado en que se guardó en nombre de microservicio, donde el microservicio puede recuperar este estado de, y si el microservicio puede reiniciar correctamente. En otras palabras, debe haber resistencia en la capacidad de proceso (el proceso puede reiniciar en cualquier momento), así como la resistencia en el estado o los datos (sin pérdida de datos y los datos permanecen coherente).

Los problemas de resistencia se agrava durante otros escenarios, como cuando se producen errores durante la actualización de la aplicación. El microservicio, trabajar con el sistema de implementación, debe determinar si puede continuar avanzar a la versión más reciente o en su lugar, revertir a una versión anterior para mantener un estado coherente. Preguntas como si están disponibles para mantener al día móvil suficientes máquinas y cómo recuperar versiones anteriores de la microservicio deben tenerse en cuenta. Esto requiere el microservicio para emitir información de estado para que la aplicación global y orchestrator pueden tomar estas decisiones.

Además, está relacionado con resistencia a los sistemas basados en nube cómo debe comportarse. Como se mencionó, un sistema basado en la nube debe adoptar errores y debe intentar recuperarse automáticamente de ellas. Por ejemplo, en caso de errores de red o un contenedor, las aplicaciones de cliente o los servicios de cliente deben tener una estrategia para volver a intentar el envío de mensajes o volver a intentar las solicitudes, ya que en muchos casos, los errores en la nube son parciales. El [implementar las aplicaciones resistentes](#implementing_resilient_apps) sección de esta guía explica cómo controlar errores parciales. Describe técnicas como reintentos con retroceso exponencial o el patrón de disyuntor en .NET Core usando las bibliotecas como [Polly](https://github.com/App-vNext/Polly), que ofrece una gran variedad de directivas para controlar este asunto.

## <a name="health-management-and-diagnostics-in-microservices"></a>Administración del estado y diagnóstico en microservicios

Puede parecer obvio y a menudo se pasa por alto, pero un microservicio debe notificar su estado y diagnóstico. En caso contrario, no hay una ligera introducción desde una perspectiva de operaciones. Correlacionar eventos de diagnóstico en un conjunto de servicios independientes y trabaja con máquina reloj inclinaciones dar sentido el orden de eventos son un desafío. En la misma manera que interactúan con un microservicio sobre acordado protocolos y formatos de datos, hay una necesidad de estandarización de inicio de sesión de estado y eventos de diagnóstico que en última instancia terminan en un almacén de eventos para consultar y ver. En un enfoque microservicios, es la clave que los distintos equipos que están de acuerdo en un formato de registro único. Debe haber un enfoque coherente para ver los eventos de diagnóstico en la aplicación.

### <a name="health-checks"></a>Comprobaciones de mantenimiento

El estado es diferente de diagnóstico. Estado trata el microservicio informan de su estado actual para que tome las medidas oportunas. Un buen ejemplo funciona con los mecanismos de actualización e implementación para mantener la disponibilidad. Aunque un servicio actualmente podría ser incorrecto debido a un bloqueo de proceso o reinicio del equipo, puede que el servicio seguirá siendo operativo. Es lo último que necesita poder establecer un rendimiento peor mediante la realización de una actualización. El mejor método consiste en realizar una investigación en primer lugar o deje tiempo para el microservicio a recuperar. Eventos de estado de un microservicio nos ayudarán a tomar decisiones informadas y, en efecto, ayudan a crear servicios de reparación automática.

En la implementación de comprobaciones de mantenimiento en la sección de servicios principales de ASP.NET de esta guía se explica cómo usar una nueva biblioteca de comprobaciones de estado de ASP.NET en su microservicios para que puede informar sobre su estado a un servicio de supervisión y tome las medidas oportunas.

### <a name="using-diagnostics-and-logs-event-streams"></a>Al utilizar secuencias de eventos de diagnósticos y registros

Registros ofrecen información sobre cómo se ejecuta una aplicación o servicio, como excepciones, advertencias y mensajes informativos simples. Normalmente, cada registro está en un formato de texto con una línea por evento, aunque excepciones también suelen mostrar el seguimiento de pila en varias líneas.

En las aplicaciones monolíticas basada en servidor, puede simplemente escribir registros en un archivo en disco (un archivo de registro) y, a continuación, analizarla con cualquier herramienta. Puesto que la ejecución de la aplicación se limita a un servidor fijo o máquina virtual, por lo general no es demasiado compleja para analizar el flujo de eventos. Sin embargo, en una aplicación distribuida que se ejecutan varios servicios a través de varios nodos en un clúster de orchestrator, poder correlacionar eventos distribuidos es un desafío.

Una aplicación basada en microservicio debería no intenta almacenar el flujo de salida de eventos o archivos de registro por sí solo e intentar ni siquiera administrar el enrutamiento de los eventos a una ubicación central. Debe ser transparente, lo que significa que cada proceso solo debe escribir su flujo de eventos en una salida estándar que debajo se recopilarán por la infraestructura de entorno de ejecución donde se está ejecutando. Un ejemplo de estos enrutadores de flujo de eventos es [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow), que recopila secuencias de eventos de varios orígenes y lo publica para sistemas de salida. Estos pueden incluir simple salida estándar para un entorno de desarrollo o sistemas de la nube, como [Application Insights](https://azure.microsoft.com/services/application-insights/), [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) (para las aplicaciones locales), y [dediagnósticosdeAzure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). También hay plataformas de análisis de registros de otros fabricantes buena y herramientas que pueden buscar, alerta, informes, y registros de monitor, incluso en tiempo real, como [Splunk](http://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Orchestrators administración de la información de estado y diagnóstico

Cuando se crea una aplicación basada en microservicio, necesita ocuparse de complejidad. Por supuesto, es fácil de tratar con un único microservicio pero docenas o cientos de tipos y miles de instancias de microservicios es un problema complejo. Casi no genere la arquitectura de microservicio, también necesita alta disponibilidad, capacidad de direccionamiento, resistencia, estado y diagnóstico si pretende crear un sistema estable y coherente.

![](./media/image22.png)

**Figura 4-22**. Una plataforma de Microservicio es fundamental para la administración del estado de la aplicación

Los problemas complejos que se muestra en la figura 4-22 son muy difíciles de resolver por sí mismo. Los equipos de desarrollo deben centrarse en solucionar problemas de negocios y crear aplicaciones personalizadas con los enfoques basados en microservicio. No debe centrarse en la solución de problemas de infraestructura compleja; Si es así, el costo de cualquier aplicación basada en microservicio sería muy gran. Por lo tanto, hay plataformas orientada a servicios de microservicio, denominadas orchestrators o clústeres de microservicio, que tratan de solucionar los problemas de disco duros de compilar y ejecutar un servicio y usar de forma eficaz los recursos de infraestructura. Esto reduce las complejidades de la creación de aplicaciones que utilizan un enfoque de microservicios.

Orchestrators diferentes podrían parecer similar, pero los diagnósticos y las comprobaciones de mantenimiento que ofrece cada uno de ellos difieren en las características y el estado de madurez, a veces, según la plataforma de sistema operativo, como se explica en la sección siguiente.

## <a name="additional-resources"></a>Recursos adicionales

-   **El Factor de doce una aplicación. XI. Registros: Tratar los registros como secuencias de eventos**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Biblioteca de EventFlow de diagnóstico de Microsoft.** Repositorio de GitHub.

    [*https://github.com/Azure/Diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **¿Qué es diagnósticos de Azure**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **Conectar los equipos de Windows para el servicio de análisis de registros de Azure**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **Registro de lo que significa: El bloque de aplicaciones de la semántica de registro mediante**
    [*https://msdn.microsoft.com/library/dn440729 (v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk.** Sitio oficial.
    [*http://www.splunk.com*](http://www.splunk.com)

-   **EventSource (clase)**. API de eventos de seguimiento para Windows (ETW) [ *https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource)




>[!div class="step-by-step"]
[Anterior] (microservice-based-composite-ui-shape-layout.md) [siguiente] (scalable-available-multi-container-microservice-applications.md)
