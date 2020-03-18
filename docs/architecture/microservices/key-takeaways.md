---
title: Puntos clave
description: Obtenga las conclusiones de la arquitectura de microservicios de .NET para la guía/e-book de aplicaciones de .NET en contenedores, a fin de echar un vistazo rápido a los problemas de alto nivel que se producen al usar una arquitectura de microservicios, como ventajas e inconvenientes, patrones DDD para diseño y desarrollo, así como resistencia, seguridad y el uso de orquestadores.
ms.date: 10/19/2018
ms.openlocfilehash: 3b8b7be9b3903c64221cba7c6abdb1e38f5d944f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674462"
---
# <a name="key-takeaways"></a>Puntos clave

A modo de resumen y puntos clave, estas son las conclusiones más importantes de esta guía.

**Ventajas del uso de contenedores.** Las soluciones basadas en contenedor permiten un gran ahorro, ya que ayudan a reducir los problemas de implementación derivados de las dependencias erróneas en los entornos de producción. Los contenedores mejoran significativamente las operaciones de DevOps y producción.

**El uso de los contenedores será generalizado.** Los contenedores basados en Docker se están convirtiendo en el estándar de facto del sector, ya que son compatibles con los proveedores más importantes de los ecosistemas de Windows y Linux, como Microsoft, Amazon AWS, Google e IBM. El uso de Docker probablemente se ampliará a centros de datos en la nube y locales.

**Los contenedores como una unidad de implementación.** Un contenedor de Docker se está convirtiendo en la unidad de implementación estándar para cualquier aplicación o servicio basados en servidor.

**Microservicios.** La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones críticas distribuidas y grandes o complejas basadas en múltiples subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, la aplicación se basa en una colección de servicios que se desarrollan, prueban, versionan, implementan y escalan por separado. Cada servicio puede incluir cualquier base de datos autónoma relacionada.

**Diseño guiado por el dominio y SOA.** Los patrones de arquitectura de microservicios se derivan de la arquitectura orientada a servicios (SOA) y del diseño guiado por el dominio (DDD). Al diseñar y desarrollar microservicios para entornos con necesidades y reglas empresariales en evolución, es importante tener en cuenta los enfoques y los patrones DDD.

**Retos de los microservicios.** Los microservicios ofrecen muchas capacidades eficaces, como la implementación independiente, los límites de subsistema seguros y la diversidad de tecnología. Sin embargo, también suponen muchos retos nuevos relacionados con el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados e independientes, la comunicación resistente entre microservicios, la coherencia final y la complejidad operativa que comporta agregar la información de registro y supervisión de varios microservicios. Estos aspectos presentan un nivel de complejidad mucho mayor que una aplicación monolítica tradicional. Como resultado, solo algunos escenarios específicos son adecuados para las aplicaciones basadas en microservicio. Estas incluyen aplicaciones grandes y complejas con varios subsistemas en evolución. En estos casos, merece la pena invertir en una arquitectura de software más compleja, ya que la agilidad y el mantenimiento de la aplicación serán mejores a largo plazo.

**Contenedores para cualquier aplicación.** Los contenedores son prácticos para los microservicios, pero también pueden resultar útiles para las aplicaciones monolíticas basadas en el .NET Framework tradicional, al usar contenedores de Windows. Las ventajas de usar Docker, como solucionar muchos problemas relacionados con el paso de la implementación a la producción y proporcionar entornos de desarrollo y prueba vanguardistas, se aplican a muchos tipos diferentes de aplicaciones.

**CLI frente a IDE.** Con herramientas de Microsoft, puede desarrollar aplicaciones .NET en contenedores con su método preferido. Puede desarrollar con una CLI y un entorno basado en editor mediante la CLI de Docker y Visual Studio Code. O bien, puede usar un enfoque centrado en IDE con Visual Studio y sus características exclusivas para Docker, como la depuración de múltiples contenedores.

**Aplicaciones en la nube resistentes.** En los sistemas basados en la nube y en los sistemas distribuidos en general, siempre hay el riesgo de error parcial. Puesto que los clientes y los servicios son procesos independientes (contenedores), es posible que un servicio no pueda responder de forma oportuna a la solicitud de un cliente. Por ejemplo, podría ser que un servicio estuviera inactivo a causa de un error parcial o por mantenimiento, que estuviera sobrecargado y respondiera lentamente a las solicitudes o bien que simplemente fuera inaccesible durante un breve tiempo debido a problemas de red. Por tanto, una aplicación basada en la nube debe estar preparada para dichos errores y disponer de una estrategia para responder a los mismos. Estas estrategias pueden incluir aplicar directivas de reintento (volver a enviar mensajes o solicitudes) e implementar patrones de interruptor para evitar una carga exponencial de solicitudes repetidas. Básicamente, las aplicaciones basadas en la nube deben tener mecanismos resistentes, ya sean personalizados o basados en la infraestructura de nube, como los de alto nivel de orquestadores o buses de servicio.

**Seguridad.** Nuestro mundo moderno de contenedores y microservicios puede exponer nuevas vulnerabilidades. Existen varias formas de implementar la seguridad de la aplicación básica, basada en la autenticación y la autorización. Sin embargo, la seguridad del contenedor debe tener en cuenta otros componentes clave que resultan en aplicaciones intrínsecamente más seguras. Un elemento fundamental de crear aplicaciones más seguras es tener una forma segura de comunicarse con otros sistemas y aplicaciones, algo que a menudo requiere credenciales, tokens, contraseñas y demás, que normalmente se denominan secretos de la aplicación. Cualquier solución segura debe seguir los procedimientos recomendados de seguridad, como cifrar secretos mientras están en tránsito y en reposo e impedir que los secretos se filtren cuando la aplicación final los consuma. Esos secretos deben almacenarse y guardarse de forma segura, como al usar Azure Key Vault.

**Orquestadores.** Los orquestadores basados en contenedores, como Azure Kubernetes Service y Azure Service Fabric, representan una parte fundamental de todo microservicio significativo y aplicación basada en contenedores. Estas aplicaciones llevan consigo gran complejidad, necesidades de escalabilidad y evolucionan constantemente. En esta guía se han presentado orquestadores y su rol en las soluciones basadas en microservicio y contenedor. Si sus necesidades de aplicación lo están dirigiendo hacia aplicaciones en contenedores complejas, le resultará útil para buscar recursos adicionales que le permitan obtener más información sobre los orquestadores.

>[!div class="step-by-step"]
>[Anterior](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
