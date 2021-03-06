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
# <a name="migrate-large-solutions-to-aspnet-core"></a><span data-ttu-id="993c4-103">Migre soluciones de gran tamaño a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="993c4-103">Migrate large solutions to ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="993c4-104">La migración de soluciones de gran tamaño desde .NET Framework a .NET core requiere cierta planeación.</span><span class="sxs-lookup"><span data-stu-id="993c4-104">Migrating large solutions from .NET Framework to .NET Core requires some planning.</span></span> <span data-ttu-id="993c4-105">Las dependencias se deben migrar o actualizar antes que los proyectos que dependen de ellas.</span><span class="sxs-lookup"><span data-stu-id="993c4-105">Dependencies must be migrated or updated before the projects that depend on them.</span></span> <span data-ttu-id="993c4-106">Hay herramientas que pueden identificar las dependencias y ofrecer ayuda con la migración a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="993c4-106">There are tools that can identify dependencies and offer help with migrating to .NET Core.</span></span> <span data-ttu-id="993c4-107">En función de la aplicación, el ámbito y los patrones de uso actuales, se pueden emplear estrategias diferentes al migrar.</span><span class="sxs-lookup"><span data-stu-id="993c4-107">Depending on the app, its scope, and current usage patterns, different strategies may be employed when migrating.</span></span> <span data-ttu-id="993c4-108">¿La migración se realiza a la vez o a lo largo del tiempo, en paralelo con el sistema actual?</span><span class="sxs-lookup"><span data-stu-id="993c4-108">Do you migrate it all at once, or over time, side-by-side with the current system?</span></span> <span data-ttu-id="993c4-109">¿Ajusta el sistema actual en el nuevo y reemplaza incrementalmente su funcionalidad?</span><span class="sxs-lookup"><span data-stu-id="993c4-109">Do you wrap the current system in the new one, and incrementally replace its functionality?</span></span>

<span data-ttu-id="993c4-110">En este capítulo, aprenderá cómo crear un plan de migración para una solución de gran tamaño, cómo usar las herramientas de para ayudar a la migración y algunas estrategias que se deben tener en cuenta para la migración.</span><span class="sxs-lookup"><span data-stu-id="993c4-110">In this chapter, you'll learn how create a migration plan for a large solution, how to use tools to help with the migration, and some strategies to consider for the migration itself.</span></span>

## <a name="references"></a><span data-ttu-id="993c4-111">Referencias</span><span class="sxs-lookup"><span data-stu-id="993c4-111">References</span></span>

- [<span data-ttu-id="993c4-112">¿Qué temas son importantes para migrar aplicaciones grandes de MVC y API Web a .NET Core?</span><span class="sxs-lookup"><span data-stu-id="993c4-112">What topics are important to migrating large MVC and Web API apps to .NET Core?</span></span>](https://twitter.com/ardalis/status/1313669040859217921)
- [<span data-ttu-id="993c4-113">Portabilidad de .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="993c4-113">Porting from .NET Framework to .NET Core</span></span>](../../core/porting/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="993c4-114">[Anterior](testing-differences.md)
>[Siguiente](identify-migration-sequence.md)</span><span class="sxs-lookup"><span data-stu-id="993c4-114">[Previous](testing-differences.md)
[Next](identify-migration-sequence.md)</span></span>
