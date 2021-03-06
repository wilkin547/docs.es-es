---
title: Diferencias de inserción de dependencias entre ASP.NET MVC y ASP.NET Core
description: Vea cómo funciona la inserción de dependencias en ASP.NET MVC y ASP.NET Core, cómo se diferencian y cómo migrar de ASP.NET MVC a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: aa1c7dd2f70e1a545352feb6560177bc6e2baa2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401779"
---
# <a name="dependency-injection-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="6197e-103">Diferencias de inserción de dependencias entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6197e-103">Dependency injection differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="6197e-104">Aunque la inserción de dependencias (DI) no está integrada en ASP.NET MVC o Web API, muchas aplicaciones lo habilitan agregando un paquete de NuGet con un contenedor de inversión de control (IOC).</span><span class="sxs-lookup"><span data-stu-id="6197e-104">Although dependency injection (DI) isn't built into ASP.NET MVC or Web API, many apps enable it by adding a NuGet package with an inversion of control (IOC) container.</span></span> <span data-ttu-id="6197e-105">A veces se conocen como contenedores de DI, para la inserción de dependencias (o la inversión).</span><span class="sxs-lookup"><span data-stu-id="6197e-105">These are sometimes referred to as DI containers, for dependency injection (or inversion).</span></span> <span data-ttu-id="6197e-106">Algunos de los contenedores más populares que se usan en las aplicaciones ASP.NET MVC incluyen:</span><span class="sxs-lookup"><span data-stu-id="6197e-106">Some of the most popular containers used in ASP.NET MVC apps include:</span></span>

- [<span data-ttu-id="6197e-107">Autofac</span><span class="sxs-lookup"><span data-stu-id="6197e-107">Autofac</span></span>](https://www.autofac.org/)
- [<span data-ttu-id="6197e-108">Unity</span><span class="sxs-lookup"><span data-stu-id="6197e-108">Unity</span></span>](https://unitycontainer.github.io/)
- [<span data-ttu-id="6197e-109">Ninject</span><span class="sxs-lookup"><span data-stu-id="6197e-109">Ninject</span></span>](http://www.ninject.org/)
- <span data-ttu-id="6197e-110">[StructureMap](http://structuremap.github.io/) *(desusado)*</span><span class="sxs-lookup"><span data-stu-id="6197e-110">[StructureMap](http://structuremap.github.io/) *(deprecated)*</span></span>
- [<span data-ttu-id="6197e-111">Windsor</span><span class="sxs-lookup"><span data-stu-id="6197e-111">Castle Windsor</span></span>](http://www.castleproject.org/projects/windsor/)

<span data-ttu-id="6197e-112">Si la aplicación de ASP.NET MVC no usa DI, probablemente querrá investigar la compatibilidad integrada para DI en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6197e-112">If your ASP.NET MVC app isn't using DI, you will probably want to investigate the built-in support for DI in ASP.NET Core.</span></span> <span data-ttu-id="6197e-113">DI promueve el acoplamiento flexible de los módulos de la aplicación y permite una mejor prueba y adherencia a principios como [Solid](https://www.weeklydevtips.com/episodes/047).</span><span class="sxs-lookup"><span data-stu-id="6197e-113">DI promotes loose coupling of modules in your app and enables better testability and adherence to principles like [SOLID](https://www.weeklydevtips.com/episodes/047).</span></span>

<span data-ttu-id="6197e-114">Si su aplicación usa DI, probablemente la mejor opción es ver si el contenedor que usa es compatible con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6197e-114">If your app does use DI, then probably your best course of action is to see if the container you're using supports ASP.NET Core.</span></span> <span data-ttu-id="6197e-115">En ese caso, es posible que pueda seguir utilizándolo y las reglas de configuración personalizadas que describen las asignaciones de tipos y la duración.</span><span class="sxs-lookup"><span data-stu-id="6197e-115">If so, you may be able to continue using it and your custom configuration rules describing your type mappings and lifetimes.</span></span>

<span data-ttu-id="6197e-116">En cualquier caso, debe considerar la posibilidad de usar la compatibilidad integrada con DI que se incluye con ASP.NET Core, ya que puede satisfacer las necesidades de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6197e-116">Either way, you should consider using the built-in support for DI that ships with ASP.NET Core, as it may meet your app's needs.</span></span>

## <a name="dependency-injection-in-aspnet-core"></a><span data-ttu-id="6197e-117">Inserción de dependencias en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6197e-117">Dependency injection in ASP.NET Core</span></span>

<span data-ttu-id="6197e-118">ASP.NET Core supone que las aplicaciones usarán DI.</span><span class="sxs-lookup"><span data-stu-id="6197e-118">ASP.NET Core assumes apps will use DI.</span></span> <span data-ttu-id="6197e-119">No está integrado en el marco de trabajo, pero es necesario para proporcionar compatibilidad con las características de .NET Framework en las aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6197e-119">It's not just built into the framework, but is required in order to bring support for framework features into your ASP.NET Core apps.</span></span> <span data-ttu-id="6197e-120">En el inicio de la aplicación, se realiza una llamada a, `ConfigureServices` que es responsable de registrar todos los tipos que el contenedor de di (colección de servicios o proveedor de servicios) puede crear e insertar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6197e-120">In app startup, a call is made to `ConfigureServices` which is responsible for registering all of the types that the DI container (service collection/service provider) can create and inject in the app.</span></span> <span data-ttu-id="6197e-121">Las características integradas ASP.NET Core como Entity Framework Core, identidad e incluso MVC se incorporan a la aplicación mediante su configuración como servicios en el `ConfigureServices` método.</span><span class="sxs-lookup"><span data-stu-id="6197e-121">Built-in ASP.NET Core features like Entity Framework Core, Identity, and even MVC are brought into the app by configuring them as services in the `ConfigureServices` method.</span></span>

<span data-ttu-id="6197e-122">Además de usar la implementación predeterminada, las aplicaciones pueden seguir usando contenedores personalizados.</span><span class="sxs-lookup"><span data-stu-id="6197e-122">In addition to using the default implementation, apps can still use custom containers.</span></span> <span data-ttu-id="6197e-123">[En la documentación se explica cómo reemplazar el contenedor de servicios predeterminado](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement).</span><span class="sxs-lookup"><span data-stu-id="6197e-123">The [documentation covers how to replace the default service container](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement).</span></span>

<span data-ttu-id="6197e-124">DI es fundamental para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6197e-124">DI is fundamental to ASP.NET Core.</span></span> <span data-ttu-id="6197e-125">Si el equipo ya no está bien en esta práctica, querrá comprenderlo antes de migrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6197e-125">If your team isn't already well-versed in this practice, you'll want to understand it before porting your app.</span></span>

## <a name="references"></a><span data-ttu-id="6197e-126">Referencias</span><span class="sxs-lookup"><span data-stu-id="6197e-126">References</span></span>

- [<span data-ttu-id="6197e-127">Inserción de dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="6197e-127">Dependency Injection in .NET</span></span>](../../core/extensions/dependency-injection.md)
- [<span data-ttu-id="6197e-128">Inserción de dependencias en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6197e-128">Dependency Injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)

>[!div class="step-by-step"]
><span data-ttu-id="6197e-129">[Anterior](serving-static-files.md)
>[Siguiente](middleware-modules-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="6197e-129">[Previous](serving-static-files.md)
[Next](middleware-modules-handlers.md)</span></span>
