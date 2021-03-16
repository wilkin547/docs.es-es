---
title: Uso de la inserción de dependencias en .NET
description: Obtenga información sobre cómo usar la inserción de dependencias en las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 11/13/2020
ms.topic: tutorial
no-loc:
- Transient
- Scoped
- Singleton
- Example
ms.openlocfilehash: d6654d5d1c8f7959e96998c18a1790cce46ebf41
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102402212"
---
# <a name="tutorial-use-dependency-injection-in-net"></a><span data-ttu-id="51f28-103">Tutorial: Uso de la inserción de dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="51f28-103">Tutorial: Use dependency injection in .NET</span></span>

<span data-ttu-id="51f28-104">En este tutorial se muestra cómo usar la [inserción de dependencias (DI) en .NET](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="51f28-104">This tutorial shows how to use [dependency injection (DI) in .NET](dependency-injection.md).</span></span> <span data-ttu-id="51f28-105">Con las *extensiones de Microsoft*, DI es un ciudadano de primera clase donde se agregan y configuran los servicios en un <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span><span class="sxs-lookup"><span data-stu-id="51f28-105">With *Microsoft Extensions*, DI is a first-class citizen where services are added and configured in an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="51f28-106">La interfaz de <xref:Microsoft.Extensions.Hosting.IHost> expone la instancia de <xref:System.IServiceProvider>, que actúa como un contenedor de todos los servicios registrados.</span><span class="sxs-lookup"><span data-stu-id="51f28-106">The <xref:Microsoft.Extensions.Hosting.IHost> interface exposes the <xref:System.IServiceProvider> instance, which acts as a container of all the registered services.</span></span>

<span data-ttu-id="51f28-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="51f28-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="51f28-108">Crear una aplicación de consola de .NET que use la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="51f28-108">Create a .NET console app that uses dependency injection</span></span>
> - <span data-ttu-id="51f28-109">Compilar y configurar un [host genérico](generic-host.md).</span><span class="sxs-lookup"><span data-stu-id="51f28-109">Build and configure a [Generic Host](generic-host.md)</span></span>
> - <span data-ttu-id="51f28-110">Escribir varias interfaces y las implementaciones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="51f28-110">Write several interfaces and corresponding implementations</span></span>
> - <span data-ttu-id="51f28-111">Usar la duración y el ámbito del servicio para DI.</span><span class="sxs-lookup"><span data-stu-id="51f28-111">Use service lifetime and scoping for DI</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51f28-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="51f28-112">Prerequisites</span></span>

- <span data-ttu-id="51f28-113">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="51f28-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or later.</span></span>
- <span data-ttu-id="51f28-114">Familiaridad con la creación de nuevas aplicaciones .NET y la instalación de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="51f28-114">Familiarity with creating new .NET applications and installing NuGet packages.</span></span>

## <a name="create-a-new-console-application"></a><span data-ttu-id="51f28-115">Creación de una nueva aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="51f28-115">Create a new console application</span></span>

<span data-ttu-id="51f28-116">Mediante el comando [dotnet new](../tools/dotnet-new.md) o un asistente para nuevo proyecto IDE, cree una nueva aplicación de consola .NET denominada **ConsoleDIExample** .</span><span class="sxs-lookup"><span data-stu-id="51f28-116">Using either the [dotnet new](../tools/dotnet-new.md) command or an IDE new project wizard, create a new .NET console application named **ConsoleDI.Example**.</span></span> <span data-ttu-id="51f28-117">Agregue el paquete NuGet [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="51f28-117">Add the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package to the project.</span></span>

## <a name="add-interfaces"></a><span data-ttu-id="51f28-118">Adición de interfaces</span><span class="sxs-lookup"><span data-stu-id="51f28-118">Add interfaces</span></span>

<span data-ttu-id="51f28-119">Agregue las siguientes interfaces al directorio raíz del proyecto:</span><span class="sxs-lookup"><span data-stu-id="51f28-119">Add the following interfaces to the project root directory:</span></span>

<span data-ttu-id="51f28-120">*IOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-120">*IOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

<span data-ttu-id="51f28-121">La interfaz `IOperation` define una única propiedad `OperationId`.</span><span class="sxs-lookup"><span data-stu-id="51f28-121">The `IOperation` interface defines a single `OperationId` property.</span></span>

<span data-ttu-id="51f28-122">*ITransientOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-122">*ITransientOperation.cs*</span></span>

<span data-ttu-id="51f28-123">:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="51f28-123">:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::</span></span>

<span data-ttu-id="51f28-124">*IScopedOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-124">*IScopedOperation.cs*</span></span>

<span data-ttu-id="51f28-125">:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="51f28-125">:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::</span></span>

<span data-ttu-id="51f28-126">*ISingletonOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-126">*ISingletonOperation.cs*</span></span>

<span data-ttu-id="51f28-127">:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="51f28-127">:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::</span></span>

<span data-ttu-id="51f28-128">Todas las subinterfaces de `IOperation` denominan su duración de servicio prevista.</span><span class="sxs-lookup"><span data-stu-id="51f28-128">All of the subinterfaces of `IOperation` name their intended service lifetime.</span></span> <span data-ttu-id="51f28-129">Por ejemplo, "Transient" o "Singleton".</span><span class="sxs-lookup"><span data-stu-id="51f28-129">For example, "Transient" or "Singleton".</span></span>

## <a name="add-default-implementation"></a><span data-ttu-id="51f28-130">Adición de la implementación predeterminada</span><span class="sxs-lookup"><span data-stu-id="51f28-130">Add default implementation</span></span>

<span data-ttu-id="51f28-131">Agregue la siguiente implementación predeterminada para las distintas operaciones:</span><span class="sxs-lookup"><span data-stu-id="51f28-131">Add the following default implementation for the various operations:</span></span>

<span data-ttu-id="51f28-132">*DefaultOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-132">*DefaultOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

<span data-ttu-id="51f28-133">`DefaultOperation` implementa todas las interfaces de marcador con nombre e inicializa la propiedad `OperationId` en los cuatro últimos caracteres de un nuevo identificador único global (GUID).</span><span class="sxs-lookup"><span data-stu-id="51f28-133">The `DefaultOperation` implements all of the named marker interfaces and initializes the `OperationId` property to the last four characters of a new globally unique identifier (GUID).</span></span>

## <a name="add-service-that-requires-di"></a><span data-ttu-id="51f28-134">Adición de un servicio que requiera DI</span><span class="sxs-lookup"><span data-stu-id="51f28-134">Add service that requires DI</span></span>

<span data-ttu-id="51f28-135">Agregue el siguiente objeto de registrador de operaciones, que actúa como un servicio para la aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="51f28-135">Add the following operation logger object, which acts as a service to the console app:</span></span>

<span data-ttu-id="51f28-136">*OperationLogger.cs*</span><span class="sxs-lookup"><span data-stu-id="51f28-136">*OperationLogger.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

<span data-ttu-id="51f28-137">`OperationLogger` define un constructor que requiere cada una de las interfaces de marcador mencionadas anteriormente, es decir `ITransientOperation`, `IScopedOperation` y `ISingletonOperation`.</span><span class="sxs-lookup"><span data-stu-id="51f28-137">The `OperationLogger` defines a constructor that requires each of the aforementioned marker interfaces, that is; `ITransientOperation`, `IScopedOperation`, and `ISingletonOperation`.</span></span> <span data-ttu-id="51f28-138">El objeto expone un método único que permite al consumidor registrar las operaciones con un parámetro `scope` determinado.</span><span class="sxs-lookup"><span data-stu-id="51f28-138">The object exposes a single method that allows the consumer to log the operations with a given `scope` parameter.</span></span> <span data-ttu-id="51f28-139">Cuando se invoca, el método `LogOperations` registra el identificador único de cada operación con la cadena de ámbito y el mensaje.</span><span class="sxs-lookup"><span data-stu-id="51f28-139">When invoked, the `LogOperations` method logs each operation's unique identifier with the scope string and message.</span></span>

## <a name="register-services-for-di"></a><span data-ttu-id="51f28-140">Registro de servicios para DI</span><span class="sxs-lookup"><span data-stu-id="51f28-140">Register services for DI</span></span>

<span data-ttu-id="51f28-141">Actualice *Program.cs* con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="51f28-141">Update *Program.cs* with the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

> <span data-ttu-id="51f28-142">Cada método de extensión `services.Add{SERVICE_NAME}` agrega servicios y potencialmente los configura.</span><span class="sxs-lookup"><span data-stu-id="51f28-142">Each `services.Add{SERVICE_NAME}` extension method adds, and potentially configures, services.</span></span> <span data-ttu-id="51f28-143">Se recomienda que las aplicaciones sigan esta convención.</span><span class="sxs-lookup"><span data-stu-id="51f28-143">We recommended that apps follow this convention.</span></span> <span data-ttu-id="51f28-144">Coloque los métodos de extensión en el espacio de nombres <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> para encapsular grupos de registros del servicio.</span><span class="sxs-lookup"><span data-stu-id="51f28-144">Place extension methods in the <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> namespace to encapsulate groups of service registrations.</span></span> <span data-ttu-id="51f28-145">La inclusión de la parte del espacio de nombres `Microsoft.Extensions.DependencyInjection` para los métodos de extensión DI también:</span><span class="sxs-lookup"><span data-stu-id="51f28-145">Including the namespace portion `Microsoft.Extensions.DependencyInjection` for DI extension methods also:</span></span>
>
> - <span data-ttu-id="51f28-146">Permite que se muestren en [IntelliSense](/visualstudio/ide/using-intellisense) sin agregar bloques `using` adicionales.</span><span class="sxs-lookup"><span data-stu-id="51f28-146">Allows them to be displayed in [IntelliSense](/visualstudio/ide/using-intellisense) without adding additional `using` blocks.</span></span>
> - <span data-ttu-id="51f28-147">Evita demasiadas instrucciones `using` en las clases `Program` o `Startup`, donde se llama normalmente a estos métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="51f28-147">Prevents excessive `using` statements in the `Program` or `Startup` classes where these extension methods are typically called.</span></span>

<span data-ttu-id="51f28-148">La aplicación:</span><span class="sxs-lookup"><span data-stu-id="51f28-148">The app:</span></span>

- <span data-ttu-id="51f28-149">Crea una instancia <xref:Microsoft.Extensions.Hosting.IHostBuilder> con la [configuración de enlazador predeterminada](generic-host.md#default-builder-settings).</span><span class="sxs-lookup"><span data-stu-id="51f28-149">Creates an <xref:Microsoft.Extensions.Hosting.IHostBuilder> instance with the [default binder settings](generic-host.md#default-builder-settings).</span></span>
- <span data-ttu-id="51f28-150">Configura los servicios y los agrega con su duración de servicio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="51f28-150">Configures services and adds them with their corresponding service lifetime.</span></span>
- <span data-ttu-id="51f28-151">Llama a <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> y asigna una instancia de <xref:Microsoft.Extensions.Hosting.IHost>.</span><span class="sxs-lookup"><span data-stu-id="51f28-151">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> and assigns an instance of <xref:Microsoft.Extensions.Hosting.IHost>.</span></span>
- <span data-ttu-id="51f28-152">Llama a `ExemplifyScoping`, pasando el <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51f28-152">Calls `ExemplifyScoping`, passing in the <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span></span>

## <a name="conclusion"></a><span data-ttu-id="51f28-153">Conclusión</span><span class="sxs-lookup"><span data-stu-id="51f28-153">Conclusion</span></span>

<span data-ttu-id="51f28-154">La aplicación muestra una salida similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51f28-154">The app displays output similar to the following example:</span></span>

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

<span data-ttu-id="51f28-155">En la salida de la aplicación, puede ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51f28-155">From the app output, you can see that:</span></span>

- <span data-ttu-id="51f28-156">Las operaciones Transient siempre son diferentes y se crea una nueva instancia con cada recuperación del servicio.</span><span class="sxs-lookup"><span data-stu-id="51f28-156">Transient operations are always different, a new instance is created with every retrieval of the service.</span></span>
- <span data-ttu-id="51f28-157">Las operaciones Scoped solo cambian con un nuevo ámbito pero son la misma instancia dentro de un ámbito.</span><span class="sxs-lookup"><span data-stu-id="51f28-157">Scoped operations change only with a new scope, but are the same instance within a scope.</span></span>
- <span data-ttu-id="51f28-158">Las operaciones Singleton siempre son las mismas y una instancia nueva solo se crea una vez.</span><span class="sxs-lookup"><span data-stu-id="51f28-158">Singleton operations are always the same, a new instance is only created once.</span></span>

## <a name="see-also"></a><span data-ttu-id="51f28-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="51f28-159">See also</span></span>

* [<span data-ttu-id="51f28-160">Instrucciones para la inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="51f28-160">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
* [<span data-ttu-id="51f28-161">Inserción de dependencias en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="51f28-161">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
