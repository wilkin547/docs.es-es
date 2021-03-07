---
title: Diferencias arquitectónicas entre ASP.NET MVC y ASP.NET Core
description: Revise las diferencias arquitectónicas entre ASP.NET y ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 96477f2393482380eee9891e9b2dbbb6445e15bd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401821"
---
# <a name="architectural-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias arquitectónicas entre ASP.NET MVC y ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Hay muchas diferencias arquitectónicas entre ASP.NET MVC en .NET Framework y ASP.NET Core. Es importante tener una visión general de estas diferencias a medida que los equipos evalúen el trabajo que supone trasladar sus aplicaciones ASP.NET MVC a ASP.NET Core. En este capítulo se examina cada una de las formas en que ASP.NET Core difiere sustancialmente de ASP.NET MVC.

## <a name="breaking-changes"></a>Últimos cambios

.NET Core es una reescritura multiplataforma de .NET Framework. Hay muchos [cambios importantes entre los dos marcos de trabajo](../../core/compatibility/fx-core.md). En las secciones siguientes se identifican las diferencias específicas entre cómo se diseñan y desarrollan las aplicaciones ASP.NET MVC y ASP.NET Core. Tenga cuidado de examinar también la documentación para determinar qué bibliotecas de Framework está usando que pueden ser necesarias para cambiar. En muchos casos, existe un paquete de NuGet de reemplazo para rellenar los huecos que quedan entre .NET Framework y .NET Core. En raras ocasiones, puede que necesite encontrar una solución de terceros o implementar código nuevo personalizado para abordar las incompatibilidades.

>[!div class="step-by-step"]
>[Anterior](additional-migration-resources.md)
>[Siguiente](app-startup-differences.md)
