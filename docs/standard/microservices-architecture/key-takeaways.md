---
title: Puntos clave
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | puntos clave
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b557d0b641bfe95c025cadb13f82c3f8927f4bc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="key-takeaways"></a>Puntos clave

Como un resumen y los puntos clave, éstas son las conclusiones más importantes de esta guía.

**Ventajas del uso de contenedores.** Soluciones basadas en el contenedor proporcionan la ventaja importante de ahorro de costos porque los contenedores son una solución de problemas de implementación causados por la ausencia de dependencias en entornos de producción. Contenedores mejoran significativamente las operaciones de DevOps y producción.

**Contenedores será ubicuos.** Contenedores de docker se está convirtiendo en el estándar de facto de la industria de contenedor, compatible con los proveedores más importantes en el ecosistema de Windows y Linux. Esto incluye Microsoft, Amazon AWS, Google y IBM. En un futuro próximo, Docker probablemente será ubicuo en centros de datos en la nube y locales.

**Contenedores como una unidad de implementación.** Un contenedor de Docker se está convirtiendo en la unidad de implementación para cualquier aplicación basada en el servidor o el servicio estándar.

**Microservicios.** La arquitectura de microservicios se está convirtiendo en el método preferido para las aplicaciones críticas distribuidas y grandes o complejas en función de varios subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicio, la aplicación se compila como una colección de servicios que pueden ser desarrollado, probado, control de versiones, implementar y escalar de forma independiente; Esto puede incluir cualquier base de datos autónomo relacionada.

**Diseño basado en dominio y SOA.** Los patrones de arquitectura de microservicios se derivan de la arquitectura orientada a servicios (SOA) y diseño basado en dominio (DDD). Al diseñar y desarrollar microservicios para entornos con evolucionando dar forma a un dominio en particular las reglas de negocios, es importante tener en cuenta DDD enfoques y patrones.

**Desafíos de Microservicios.** Microservicios ofrecen muchas capacidades eficaces, como la implementación independiente, los límites de subsistema seguro y diversidad de tecnología. Sin embargo, también activan muchos nuevos desafíos relacionados con el desarrollo de aplicaciones distribuidas, como fragmentado y modelos de datos independientes, resistente comunicación entre microservicios y coherencia definitiva, complejidad operativa que es el resultado de agregar información de registro y supervisión de varios microservicios. Estos aspectos presentan un mayor nivel de complejidad que una aplicación monolítico tradicional. Como resultado, solo los escenarios específicos son adecuados para aplicaciones basadas en microservicio. Estas soluciones incluyen aplicaciones grandes y complejas con varios subsistemas en constante evolución; en estos casos, merece la pena invertir en una arquitectura de software más compleja, ya que proporcionará a largo plazo mejor agilidad y mantenimiento de la aplicación.

**Contenedores para cualquier aplicación.** Los contenedores son convenientes para microservicios, pero no son exclusivos para ellos. Contenedores también pueden usarse con aplicaciones monolíticas, incluidas las aplicaciones heredadas basado en .NET Framework tradicionales y y modernizado a través de contenedores de Windows. Las ventajas de usar Docker, como muchos problemas de implementación de producción y proporcionar entornos de desarrollo y prueba del estado de la técnica, se aplican a muchos tipos diferentes de aplicaciones.

**CLI frente a IDE.** Con herramientas de Microsoft, puede desarrollar aplicaciones .NET en contenedores con su método preferido. Puede desarrollar con una CLI y un entorno basado en el editor mediante la CLI de Docker y el código de Visual Studio. O bien, puede usar un enfoque centrado en IDE con Visual Studio y sus características exclusivas de Docker, como como poder depurar aplicaciones de contenedor de varios.

**Aplicaciones de nube resistentes.** En sistemas basados en la nube y sistemas distribuidos en general, hay siempre el riesgo de error parcial. Puesto que los clientes y servicios son procesos independientes (contenedores), es posible que un servicio no pueda responder de forma oportuna a solicitud del cliente. Por ejemplo, podría ser un servicio inactivo debido a un error parcial o mantenimiento; el servicio podría estar sobrecargado y responde muy lentamente a las solicitudes; o bien, puede que simplemente no sea accesible durante un breve tiempo debido a problemas de red. Por lo tanto, una aplicación basada en la nube debe adoptar dichos errores y tener una estrategia para responder a los errores. Estas estrategias pueden incluir directivas de reintento (volver a enviar mensajes o volver a intentar solicitudes) y patrones de implementación-disyuntor para evitar exponencial de carga de solicitudes repetidas. Básicamente, las aplicaciones basadas en la nube deben tener mecanismos resistentes, ya sea personalizados los o los que se basa en la infraestructura de nube, como los marcos de trabajo de alto nivel de orchestrators o bus de servicio.

**Seguridad.** Nuestro mundo moderno de contenedores y microservicios puede exponer nuevas vulnerabilidades. Seguridad de la aplicación básica se basa en la autenticación y autorización. Existen varias maneras para implementar estos. Sin embargo, la seguridad de contenedor incluye otros componentes principales que dan como resultado aplicaciones intrínsecamente más seguras. Un elemento fundamental de la creación de aplicaciones más seguras es tener una forma segura de comunicarse con otros sistemas y aplicaciones, algo que a menudo requiere credenciales, símbolos (token), contraseñas y otros tipos de información confidencial, normalmente se denomina secretos de la aplicación. Cualquier solución segura debe seguir los procedimientos recomendados de seguridad, como el cifrado de secretos mientras están en tránsito; cifrado de secretos en reposo; e impide que los secretos involuntariamente pierde cuando consumida por la aplicación final. Los secretos deben almacenan y mantienen seguros en algún lugar. Para mejorar la seguridad, puede sacar partido de la infraestructura de su orchestrator elegido, o de infraestructura de la nube como almacén de claves de Azure y las maneras en que proporciona para que el código de aplicación utilizarlo.

**Orchestrators.** Son indispensables para cualquier aplicación de microservicio para entornos de producción y para cualquier contenedor varios orchestrators basado en el contenedor como los proporcionados en el servicio de contenedor de Azure (Kubernetes, Mesos DC/OS y Docker Swarm) y Azure Service Fabric aplicación con una complejidad significativa y necesidades de escalabilidad, constante evolución. Esta guía presenta orchestrators y su función en las soluciones basadas en microservicio y contenedor. Si sus necesidades de aplicación se mueve hacia complejas aplicaciones en contenedores, le resultará útil para buscar recursos adicionales para obtener más información acerca de orchestrators

>[!div class="step-by-step"]
[Anterior] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
