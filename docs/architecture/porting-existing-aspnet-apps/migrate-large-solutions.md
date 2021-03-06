---
title: Migre soluciones de gran tamaño a ASP.NET Core
description: Un vistazo a cómo migrar aplicaciones grandes de ASP.NET MVC a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d3ebd71213e074ce80dc83fc3230c4e365275ad3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401728"
---
# <a name="migrate-large-solutions-to-aspnet-core"></a>Migre soluciones de gran tamaño a ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La migración de soluciones de gran tamaño desde .NET Framework a .NET core requiere cierta planeación. Las dependencias se deben migrar o actualizar antes que los proyectos que dependen de ellas. Hay herramientas que pueden identificar las dependencias y ofrecer ayuda con la migración a .NET Core. En función de la aplicación, el ámbito y los patrones de uso actuales, se pueden emplear estrategias diferentes al migrar. ¿La migración se realiza a la vez o a lo largo del tiempo, en paralelo con el sistema actual? ¿Ajusta el sistema actual en el nuevo y reemplaza incrementalmente su funcionalidad?

En este capítulo, aprenderá cómo crear un plan de migración para una solución de gran tamaño, cómo usar las herramientas de para ayudar a la migración y algunas estrategias que se deben tener en cuenta para la migración.

## <a name="references"></a>Referencias

- [¿Qué temas son importantes para migrar aplicaciones grandes de MVC y API Web a .NET Core?](https://twitter.com/ardalis/status/1313669040859217921)
- [Portabilidad de .NET Framework a .NET Core](../../core/porting/index.md)

>[!div class="step-by-step"]
>[Anterior](testing-differences.md)
>[Siguiente](identify-migration-sequence.md)
