---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665624"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="03af9-104">Recorte de implementaciones autocontenidas y ejecutables</span><span class="sxs-lookup"><span data-stu-id="03af9-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="03af9-105">Al publicar una aplicación autocontenida, el tiempo de ejecución de .NET Core se agrupa junto con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03af9-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="03af9-106">Esta agrupación agrega una cantidad considerable de contenido a la aplicación empaquetada.</span><span class="sxs-lookup"><span data-stu-id="03af9-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="03af9-107">En lo que respecta a la implementación de la aplicación, el tamaño suele ser un factor importante.</span><span class="sxs-lookup"><span data-stu-id="03af9-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="03af9-108">Mantener lo más pequeño posible el tamaño de la aplicación del paquete suele ser un objetivo para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="03af9-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="03af9-109">En función de la complejidad de la aplicación, solo se necesita un subconjunto del tiempo de ejecución para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="03af9-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="03af9-110">Estas partes sin usar del tiempo de ejecución no son necesarias y se pueden recortar de la aplicación empaquetada.</span><span class="sxs-lookup"><span data-stu-id="03af9-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="03af9-111">El recorte es una característica experimental en .NET Core 3.1 y _solo_ está disponible para las aplicaciones que se publican autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="03af9-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="03af9-112">Recorte de la aplicación</span><span class="sxs-lookup"><span data-stu-id="03af9-112">Trim your application</span></span>

<span data-ttu-id="03af9-113">En el ejemplo siguiente se muestra cómo recortar la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md):</span><span class="sxs-lookup"><span data-stu-id="03af9-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="03af9-114">La característica recorte funciona examinando los archivos binarios de la aplicación para descubrir y compilar un gráfico de los ensamblados en tiempo de ejecución necesarios.</span><span class="sxs-lookup"><span data-stu-id="03af9-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="03af9-115">Los ensamblados en tiempo de ejecución restantes a los que no se hace referencia se recortan.</span><span class="sxs-lookup"><span data-stu-id="03af9-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="03af9-116">Recorte de incidencias al usar reflexión</span><span class="sxs-lookup"><span data-stu-id="03af9-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="03af9-117">Hay escenarios en los que la función de recorte no podrá detectar referencias.</span><span class="sxs-lookup"><span data-stu-id="03af9-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="03af9-118">Por ejemplo, una aplicación que utiliza reflexión podría encontrarse con esta incidencia porque la dependencia del ensamblado solo se conocerá en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03af9-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="03af9-119">El recorte es solo un problema si el uso de la reflexión depende de un ensamblado en tiempo de ejecución al que no se hace referencia directamente.</span><span class="sxs-lookup"><span data-stu-id="03af9-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="03af9-120">Tenga en cuenta que es posible que el código de la aplicación no esté usando la reflexión directamente, sino que lo haga un ensamblado de terceros al que haga referencia.</span><span class="sxs-lookup"><span data-stu-id="03af9-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="03af9-121">Cuando el código hace referencia a una API mediante reflexión y no se quiere que el enlazador recorte el ensamblado que contiene esa API, se puede modificar el archivo del proyecto para excluir el ensamblado del proceso de recorte.</span><span class="sxs-lookup"><span data-stu-id="03af9-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="03af9-122">En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:</span><span class="sxs-lookup"><span data-stu-id="03af9-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="03af9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="03af9-123">See also</span></span>

- [<span data-ttu-id="03af9-124">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="03af9-124">.NET Core application deployment</span></span>](index.md)
