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
# <a name="architectural-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="4b154-103">Diferencias arquitectónicas entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b154-103">Architectural differences between ASP.NET MVC and ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4b154-104">Hay muchas diferencias arquitectónicas entre ASP.NET MVC en .NET Framework y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b154-104">There are many architectural differences between ASP.NET MVC on .NET Framework and ASP.NET Core.</span></span> <span data-ttu-id="4b154-105">Es importante tener una visión general de estas diferencias a medida que los equipos evalúen el trabajo que supone trasladar sus aplicaciones ASP.NET MVC a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b154-105">It's important to have a broad understanding of these differences as teams evaluate the work involved in porting their ASP.NET MVC apps to ASP.NET Core.</span></span> <span data-ttu-id="4b154-106">En este capítulo se examina cada una de las formas en que ASP.NET Core difiere sustancialmente de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="4b154-106">This chapter looks at each of the ways in which ASP.NET Core differs substantially from ASP.NET MVC.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="4b154-107">Últimos cambios</span><span class="sxs-lookup"><span data-stu-id="4b154-107">Breaking changes</span></span>

<span data-ttu-id="4b154-108">.NET Core es una reescritura multiplataforma de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b154-108">.NET Core is a cross-platform rewrite of .NET Framework.</span></span> <span data-ttu-id="4b154-109">Hay muchos [cambios importantes entre los dos marcos de trabajo](../../core/compatibility/fx-core.md).</span><span class="sxs-lookup"><span data-stu-id="4b154-109">There are many [breaking changes between the two frameworks](../../core/compatibility/fx-core.md).</span></span> <span data-ttu-id="4b154-110">En las secciones siguientes se identifican las diferencias específicas entre cómo se diseñan y desarrollan las aplicaciones ASP.NET MVC y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b154-110">The following sections identify specific differences between how ASP.NET MVC and ASP.NET Core apps are designed and developed.</span></span> <span data-ttu-id="4b154-111">Tenga cuidado de examinar también la documentación para determinar qué bibliotecas de Framework está usando que pueden ser necesarias para cambiar.</span><span class="sxs-lookup"><span data-stu-id="4b154-111">Take care to also examine the documentation to determine which framework libraries you're using that may need to change.</span></span> <span data-ttu-id="4b154-112">En muchos casos, existe un paquete de NuGet de reemplazo para rellenar los huecos que quedan entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b154-112">In many cases, a replacement NuGet package exists to fill in any gaps left between .NET Framework and .NET Core.</span></span> <span data-ttu-id="4b154-113">En raras ocasiones, puede que necesite encontrar una solución de terceros o implementar código nuevo personalizado para abordar las incompatibilidades.</span><span class="sxs-lookup"><span data-stu-id="4b154-113">In rare cases, you may need to find a third-party solution or implement new custom code to address incompatibilities.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4b154-114">[Anterior](additional-migration-resources.md)
>[Siguiente](app-startup-differences.md)</span><span class="sxs-lookup"><span data-stu-id="4b154-114">[Previous](additional-migration-resources.md)
[Next](app-startup-differences.md)</span></span>
