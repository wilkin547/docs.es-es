---
title: Resumen
description: Un resumen y un conjunto de impresiones clave para trasladar las aplicaciones ASP.NET MVC y Web API 2 a ASP.NET Core.
author: ardalis
ms.date: 12/16/2020
ms.openlocfilehash: 596ab8621008d1cdc16d841e8faede5f4a1fdd16
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401532"
---
# <a name="summary"></a>Resumen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En este libro, ha recibido los recursos necesarios para decidir si tiene sentido migrar las aplicaciones existentes de ASP.NET de su organización que se ejecutan en .NET Framework a ASP.NET Core. Ha aprendido acerca de las [consideraciones importantes](migration-considerations.md) para elegir cuándo tiene sentido migrar a .net Core y cuándo puede ser adecuado conservar (parte de) la aplicación en .NET Framework. Existen diferencias entre las versiones de .NET Core y sus funcionalidades y compatibilidad con .NET Framework, y aprendió [a elegir la versión correcta de .net Core para la aplicación](choose-net-core-version.md).

La migración de una aplicación grande a menudo conlleva una cantidad equitativa de riesgo y esfuerzo. Aprendió a mitigar este riesgo mediante el uso de una o varias [estrategias de migración incremental](incremental-migration-strategies.md) junto con varias [estrategias de implementación](deployment-strategies.md) para mantener las aplicaciones migradas parcialmente que se ejecutan en producción.

Existen muchas [diferencias arquitectónicas entre ASP.net y ASP.net Core](architectural-differences.md). En el capítulo 2, ha aprendido muchas de estas diferencias y cómo se relacionan con la migración de su aplicación. En este capítulo se trata todo, desde el [Inicio](app-startup-differences.md) de la aplicación y el [middleware](middleware-modules-handlers.md) de bajo nivel hasta las diferencias de [controlador](controller-differences.md) y [API Web](webapi-differences.md) de alto nivel y las nuevas características que permiten [escenarios de prueba mucho mejores](testing-differences.md).

A menudo, las aplicaciones de gran tamaño se componen de muchos proyectos y paquetes, y las dependencias pueden desempeñar un papel importante a la hora de determinar la facilidad o la migración difícil. El [capítulo 3](migrate-large-solutions.md) le ha ayudado [a identificar la secuencia en la que se van a migrar los proyectos](identify-migration-sequence.md) y [Cómo comprender y actualizar las dependencias de la aplicación](understand-update-dependencies.md). También se detallan [estrategias adicionales para migrar aplicaciones mientras se mantienen en producción](strategies-migrating-in-production.md).

En [el capítulo 4, vio cómo se migró una aplicación de referencia MVC de ASP.net real a ASP.net Core](example-migration-eshop.md). En este capítulo se incluye un desglose detallado de todos los cambios necesarios para realizar la aplicación existente y trasladarla para que se ejecute en ASP.NET Core. Vuelva a consultarlo si tiene preguntas específicas sobre el proceso de portabilidad y algunos de sus detalles más específicos.

Por último, [capítulo 5 escenarios de implementación específicos detallados centrados en IIS](deployment-scenarios.md). Vio cómo puede usar el servidor Web de IIS existente para hospedar partes de la aplicación que se han trasladado a ASP.NET Core manteniendo la coherencia de las direcciones URL públicas de la aplicación. IIS incluye una gran compatibilidad para la reescritura de direcciones URL y el enrutamiento de solicitudes que permite hospedar varias versiones del sitio en paralelo, o incluso en servidores diferentes, sin cambios en las direcciones URL de acceso público que expone la aplicación.

>[!div class="step-by-step"]
>[Anterior](deployment-scenarios.md)
