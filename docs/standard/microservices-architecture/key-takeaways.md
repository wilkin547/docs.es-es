---
title: Puntos clave
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Puntos clave
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 880f99228dbfe7374878b497582ccf540658fc12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578188"
---
# <a name="key-takeaways"></a>Puntos clave

A modo de resumen y puntos clave, estas son las conclusiones más importantes de esta guía.

**Ventajas del uso de contenedores.** La gran ventaja que ofrecen las soluciones basadas en contenedor es el ahorro, porque con los contenedores se solucionan los problemas de implementación provocados por la falta de dependencias en entornos de producción. Los contenedores mejoran significativamente las operaciones de DevOps y producción.

**El uso de los contenedores será generalizado.** Los contenedores basados en Docker se están convirtiendo en el estándar de facto del sector de los contenedores, ya que son compatibles con los proveedores más importantes de los ecosistemas de Windows y Linux. Esto incluye Microsoft, Amazon AWS, Google e IBM. En un futuro próximo, el uso de Docker probablemente se ampliará a centros de datos en la nube y locales.

**Los contenedores como una unidad de implementación.** Un contenedor de Docker se está convirtiendo en la unidad de implementación estándar para cualquier aplicación o servicio basados en servidor.

**Microservicios.** La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones críticas distribuidas y grandes o complejas basadas en múltiples subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, la aplicación se crea como una colección de servicios que se pueden desarrollar, probar, versionear, implementar y escalar de forma independiente; esto puede incluir cualquier base de datos autónoma relacionada.

**Diseño guiado por el dominio y SOA.** Los patrones de arquitectura de microservicios se derivan de la arquitectura orientada a servicios (SOA) y del diseño guiado por el dominio (DDD). Al diseñar y desarrollar microservicios para entornos con reglas empresariales en evolución que dan forma a un dominio en particular, es importante tener en cuenta los enfoques y los patrones DDD.

**Retos de los microservicios.** Los microservicios ofrecen muchas capacidades eficaces, como la implementación independiente, los límites de subsistema seguros y la diversidad de tecnología. Sin embargo, también suponen muchos retos nuevos relacionados con el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados e independientes, la comunicación resistente entre microservicios, la coherencia final y la complejidad operativa que comporta agregar la información de registro y supervisión de varios microservicios. Estos aspectos presentan un mayor nivel de complejidad que una aplicación monolítica tradicional. Como resultado, solo algunos escenarios específicos son adecuados para las aplicaciones basadas en microservicio. Aquí se incluyen las aplicaciones grandes y complejas con varios subsistemas en constante evolución; en estos casos, merece la pena invertir en una arquitectura de software más compleja, ya que la agilidad y el mantenimiento de la aplicación serán mejores a largo plazo.

**Contenedores para cualquier aplicación.** Los contenedores son convenientes para los microservicios, pero no son exclusivos para ellos. Los contenedores también pueden usarse con aplicaciones monolíticas, incluidas las aplicaciones heredadas basadas en el .NET Framework tradicional y modernizadas a través de contenedores de Windows. Las ventajas de usar Docker, como solucionar muchos problemas relacionados con el paso de la implementación a la producción y proporcionar entornos de desarrollo y prueba vanguardistas, se aplican a muchos tipos diferentes de aplicaciones.

**CLI frente a IDE.** Con herramientas de Microsoft, puede desarrollar aplicaciones .NET en contenedores con su método preferido. Puede desarrollar con una CLI y un entorno basado en editor mediante la CLI de Docker y Visual Studio Code. O bien, puede usar un enfoque centrado en IDE con Visual Studio y sus características exclusivas para Docker, como poder depurar aplicaciones de múltiples contenedores.

**Aplicaciones en la nube resistentes.** En los sistemas basados en la nube y en los sistemas distribuidos en general, siempre hay el riesgo de error parcial. Puesto que los clientes y los servicios son procesos independientes (contenedores), es posible que un servicio no pueda responder de forma oportuna a la solicitud de un cliente. Por ejemplo, podría ser que un servicio estuviera inactivo a causa de un error parcial o por mantenimiento, que estuviera sobrecargado y respondiera muy lentamente a las solicitudes o bien que simplemente fuera inaccesible durante un breve tiempo debido a problemas de red. Por tanto, una aplicación basada en la nube debe estar preparada para dichos errores y disponer de una estrategia para responder a los mismos. Estas estrategias pueden incluir aplicar directivas de reintento (volver a enviar mensajes o solicitudes) e implementar patrones de interruptor para evitar una carga exponencial de solicitudes repetidas. Básicamente, las aplicaciones basadas en la nube deben tener mecanismos resistentes, ya sean personalizados o basados en la infraestructura de nube, como los marcos de alto nivel de orquestadores o buses de servicio.

**Seguridad.** Nuestro mundo moderno de contenedores y microservicios puede exponer nuevas vulnerabilidades. La seguridad de la aplicación básica se basa en la autenticación y la autorización; existen varias maneras de implementarlas. Sin embargo, la seguridad del contenedor incluye otros componentes clave que resultan en aplicaciones intrínsecamente más seguras. Un elemento fundamental de crear aplicaciones más seguras es tener una forma segura de comunicarse con otros sistemas y aplicaciones, algo que a menudo requiere credenciales, tokens, contraseñas y otros tipos de información confidencial, que normalmente se denominan secretos de la aplicación. Cualquier solución segura debe seguir los procedimientos recomendados de seguridad, como cifrar secretos mientras están en tránsito, cifrar secretos en reposo e impedir que los secretos se filtren involuntariamente cuando la aplicación final los consuma. Estos secretos deben almacenarse y mantenerse seguros en algún lugar. Para mejorar la seguridad, puede sacar partido de la infraestructura de su orquestador elegido o de una infraestructura en la nube, como Azure Key Vault, y las maneras que proporciona para que el código de aplicación la use.

**Orquestadores.** Los orquestadores basados en contenedor, como los que se proporcionan en Azure Container Service (Kubernetes, Mesos DC/OS y Docker Swarm) y en Azure Service Fabric, son indispensables para cualquier aplicación basada en microservicio y preparada para entornos de producción y para cualquier aplicación de múltiples contenedores con una complejidad significativa, necesidades de escalabilidad y evolución constante. En esta guía se han presentado orquestadores y su rol en las soluciones basadas en microservicio y contenedor. Si sus necesidades de aplicación lo están dirigiendo hacia aplicaciones en contenedores complejas, le resultará útil para buscar recursos adicionales que le permitan obtener más información sobre los orquestadores

>[!div class="step-by-step"]
[Previous] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
