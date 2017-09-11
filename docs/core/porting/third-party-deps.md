---
title: "Migración a .NET Core - Análisis de las dependencias de terceros"
description: "Migración a .NET Core - Análisis de las dependencias de terceros"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a074978f2817abafa7b8a9fefe7c67c9c52195b3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="49fdc-104">Migración a .NET Core - Análisis de las dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="49fdc-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="49fdc-105">El primer paso en el proceso de conversión es comprender las dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="49fdc-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="49fdc-106">Debe averiguar cuáles de ellos, si los hay, todavía no se ejecuta en .NET Core y desarrollar un plan de contingencia para aquellos que no se ejecutan en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49fdc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="49fdc-107">Prerequisites</span></span>

<span data-ttu-id="49fdc-108">En este artículo se supone que usa Windows y Visual Studio, y que tiene un código que se ejecuta en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49fdc-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="49fdc-109">Análisis de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="49fdc-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="49fdc-110">Es muy fácil analizar los paquetes NuGet para la portabilidad.</span><span class="sxs-lookup"><span data-stu-id="49fdc-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="49fdc-111">Como un paquete NuGet es en sí mismo un conjunto de carpetas que contienen los ensamblados específicos de la plataforma, todo lo que tiene que hacer es comprobar si hay una carpeta que contiene un ensamblado de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="49fdc-112">La inspección de las carpetas de paquetes NuGet es mucho más sencillo con la herramienta [Explorador de paquetes NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="49fdc-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="49fdc-113">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="49fdc-113">Here's how to do it.</span></span>

1. <span data-ttu-id="49fdc-114">Descargue y abra el Explorador de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="49fdc-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="49fdc-115">Haga clic en "Open package from online feed" (Abrir paquete de fuente en línea).</span><span class="sxs-lookup"><span data-stu-id="49fdc-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="49fdc-116">Busque el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="49fdc-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="49fdc-117">Expanda la carpeta "lib" en la parte derecha y examine los nombres de carpeta.</span><span class="sxs-lookup"><span data-stu-id="49fdc-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="49fdc-118">También puede ver lo que admite un paquete en [nuget.org](https://www.nuget.org/) bajo la sección **Dependencias** de la página.</span><span class="sxs-lookup"><span data-stu-id="49fdc-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="49fdc-119">En cualquier caso, debe buscar una carpeta o una entrada en [nuget.org](https://www.nuget.org/) con cualquiera de los nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="49fdc-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="49fdc-120">Estos son los Moniker de la versión de .NET Framework de destino (TFM) que se asignan a las versiones de los perfiles del [estándar .NET](../../standard/net-standard.md) y de la Biblioteca de clases portables (PCL) que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="49fdc-121">Tenga en cuenta que `netcoreapp1.0`, mientras sea compatible, es para aplicaciones y no para bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="49fdc-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="49fdc-122">Aunque no hay ningún problema con el uso de una biblioteca que está basada en `netcoreapp1.0`, dicha biblioteca solo está diseñada *para* el consumo por otras aplicaciones `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="49fdc-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="49fdc-123">También hay algunos TFM heredados utilizados en versiones preliminares de .NET Core que pueden ser compatibles:</span><span class="sxs-lookup"><span data-stu-id="49fdc-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="49fdc-124">**Aunque es probable que estos funcionen con el código, no hay ninguna garantía de compatibilidad**.</span><span class="sxs-lookup"><span data-stu-id="49fdc-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="49fdc-125">Los paquetes con estos TFM se crearon con paquetes de .NET Core de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="49fdc-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="49fdc-126">Tome nota de cuando paquetes como estos se actualizan para estar basados en `netstandard`, y de si lo hacen.</span><span class="sxs-lookup"><span data-stu-id="49fdc-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="49fdc-127">Para utilizar un paquete destinado a una PCL tradicional o .NET Core de versión preliminar, debe usar la directiva `imports` en su archivo `project.json`.</span><span class="sxs-lookup"><span data-stu-id="49fdc-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="49fdc-128">Qué hacer cuando su dependencia del paquete NuGet no se ejecuta en .NET Core</span><span class="sxs-lookup"><span data-stu-id="49fdc-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="49fdc-129">Hay algunas cosas que puede hacer si un paquete NuGet en el que depende no se ejecuta en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="49fdc-130">Si el proyecto es de código abierto y está hospedado en algún lugar como GitHub, puede implicar directamente a los programadores.</span><span class="sxs-lookup"><span data-stu-id="49fdc-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="49fdc-131">Póngase en contacto con el autor en [nuget.org](https://www.nuget.org/) buscando el paquete y haciendo clic en "Contact Owners" (Ponerse en contacto con los propietarios) a la izquierda de la página del paquete.</span><span class="sxs-lookup"><span data-stu-id="49fdc-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="49fdc-132">Puede buscar otro paquete que se ejecuta en .NET Core que realiza la misma tarea que el paquete que estaba utilizando.</span><span class="sxs-lookup"><span data-stu-id="49fdc-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="49fdc-133">Puede intentar volver a escribir el código de lo que hacía el paquete usted mismo.</span><span class="sxs-lookup"><span data-stu-id="49fdc-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="49fdc-134">Puede eliminar la dependencia en el paquete mediante el cambio de la funcionalidad de la aplicación, al menos hasta que esté disponible una versión compatible del paquete.</span><span class="sxs-lookup"><span data-stu-id="49fdc-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="49fdc-135">Recuerde que los responsables del mantenimiento del proyecto de código abierto y los editores de paquetes NuGet suelen ser voluntarios que contribuyen porque están al cuidado de dominio determinado, lo hacen de forma gratuita y a menudo tienen otro trabajo durante el día.</span><span class="sxs-lookup"><span data-stu-id="49fdc-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="49fdc-136">Si accede a ellos, puede comenzar con una declaración positiva sobre la biblioteca antes de preguntarles sobre la compatibilidad de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="49fdc-137">Si no puede resolver el problema con las sugerencias anteriores, tendrá que realizar la portabilidad a .NET Core en otro momento.</span><span class="sxs-lookup"><span data-stu-id="49fdc-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="49fdc-138">El equipo de .NET le gustaría saber qué bibliotecas son las más importantes para que sean compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49fdc-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="49fdc-139">También puede enviarnos un correo electrónico a dotnet@microsoft.com sobre las bibliotecas que le gustaría utilizar.</span><span class="sxs-lookup"><span data-stu-id="49fdc-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="49fdc-140">Análisis de dependencias que no son paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="49fdc-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="49fdc-141">Puede que tenga una dependencia que no sea un paquete NuGet, como un archivo DLL en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="49fdc-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="49fdc-142">La única manera de determinar la portabilidad de esa dependencia es ejecutar la [herramienta ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="49fdc-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="49fdc-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="49fdc-143">Next steps</span></span>

<span data-ttu-id="49fdc-144">Si está realizando la portabilidad de una biblioteca, consulte [Porting your Libraries](libraries.md) (Portabilidad de las bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="49fdc-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>

