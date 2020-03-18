---
title: Dependencias y bibliotecas de .NET
description: Procedimientos recomendados para administrar las dependencias de NuGet en las bibliotecas de. NET.
ms.date: 10/02/2018
ms.openlocfilehash: 6a260b54c45a0cd231059ab3bc6f2707ef7fb20e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731479"
---
# <a name="dependencies"></a><span data-ttu-id="2600d-103">Dependencias</span><span class="sxs-lookup"><span data-stu-id="2600d-103">Dependencies</span></span>

<span data-ttu-id="2600d-104">La principal manera de agregar dependencias a una biblioteca de .NET es hacer referencia a paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="2600d-104">The primary way of adding dependencies to a .NET library is referencing NuGet packages.</span></span> <span data-ttu-id="2600d-105">Las referencias de los paquetes NuGet permiten reutilizar y aprovechar rápidamente la funcionalidad ya escrita, pero son una fuente común de problemas para los desarrolladores. NET.</span><span class="sxs-lookup"><span data-stu-id="2600d-105">NuGet package references allow you to quickly reuse and leverage already written functionality, but they're a common source of friction for .NET developers.</span></span> <span data-ttu-id="2600d-106">La administración correcta de las dependencias es importante para evitar que los cambios en otras bibliotecas de .NET interrumpan la biblioteca de .NET y viceversa.</span><span class="sxs-lookup"><span data-stu-id="2600d-106">Correctly managing dependencies is important to prevent changes in other .NET libraries from breaking your .NET library, and vice versa!</span></span>

## <a name="diamond-dependencies"></a><span data-ttu-id="2600d-107">Dependencias de rombo</span><span class="sxs-lookup"><span data-stu-id="2600d-107">Diamond dependencies</span></span>

<span data-ttu-id="2600d-108">Es una situación común para un proyecto de .NET tener varias versiones de un paquete en el árbol de dependencias.</span><span class="sxs-lookup"><span data-stu-id="2600d-108">It's a common situation for a .NET project to have multiple versions of a package in its dependency tree.</span></span> <span data-ttu-id="2600d-109">Por ejemplo, una aplicación depende de dos paquetes NuGet, cada uno de los cuales depende de las diferentes versiones del mismo paquete.</span><span class="sxs-lookup"><span data-stu-id="2600d-109">For example, an app depends on two NuGet packages, each of which depends on different versions of the same package.</span></span> <span data-ttu-id="2600d-110">Ahora existe una dependencia de rombo en el gráfico de dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2600d-110">A diamond dependency now exists in the app's dependency graph.</span></span>

<span data-ttu-id="2600d-111">![Dependencias de rombo](./media/dependencies/diamond-dependency.png "Dependencias de rombo")</span><span class="sxs-lookup"><span data-stu-id="2600d-111">![Diamond dependency](./media/dependencies/diamond-dependency.png "Diamond dependency")</span></span>

<span data-ttu-id="2600d-112">En el momento de la compilación, NuGet analiza todos los paquetes de los que depende un proyecto, incluidas las dependencias de dependencias.</span><span class="sxs-lookup"><span data-stu-id="2600d-112">At build time, NuGet analyzes all the packages that a project depends on, including the dependencies of dependencies.</span></span> <span data-ttu-id="2600d-113">Cuando se detectan varias versiones de un paquete, se evalúan las reglas para elegir una.</span><span class="sxs-lookup"><span data-stu-id="2600d-113">When multiple versions of a package are detected, rules are evaluated to pick one.</span></span> <span data-ttu-id="2600d-114">La unificación de paquetes es necesaria porque la ejecutan de versiones en paralelo de un ensamblado en la misma aplicación es problemática en. NET.</span><span class="sxs-lookup"><span data-stu-id="2600d-114">Unifying packages is necessary because running side-by-side versions of an assembly in the same application is problematic in .NET.</span></span>

<span data-ttu-id="2600d-115">La mayoría de las dependencias de rombo se resuelven con facilidad; sin embargo, pueden crear problemas en determinadas circunstancias:</span><span class="sxs-lookup"><span data-stu-id="2600d-115">Most diamond dependencies are easily resolved; however, they can create issues in certain circumstances:</span></span>

1. <span data-ttu-id="2600d-116">**Las referencias de paquetes NuGet en conflicto** impiden que una versión se resuelva durante la restauración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="2600d-116">**Conflicting NuGet package references** prevent a version from being resolved during package restore.</span></span>
2. <span data-ttu-id="2600d-117">**Los cambios importantes entre las versiones** provocan errores y excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2600d-117">**Breaking changes between the versions** cause bugs and exceptions at runtime.</span></span>
3. <span data-ttu-id="2600d-118">**El ensamblado del paquete tiene un nombre seguro**, la versión del ensamblado cambió y la aplicación se ejecuta en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2600d-118">**The package assembly is strong named**, the assembly version changed, and the app is running on the .NET Framework.</span></span> <span data-ttu-id="2600d-119">Se necesitan redirecciones de enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2600d-119">Assembly binding redirects are required.</span></span>

<span data-ttu-id="2600d-120">No es posible saber qué paquetes se utilizarán junto con los suyos.</span><span class="sxs-lookup"><span data-stu-id="2600d-120">It's not possible to know what packages will be used alongside your own.</span></span> <span data-ttu-id="2600d-121">Una buena forma de reducir la probabilidad de que una dependencia de rombo interrumpa la biblioteca es minimizar el número de paquetes de los que usted depende.</span><span class="sxs-lookup"><span data-stu-id="2600d-121">A good way to reduce the likelihood of a diamond dependency breaking your library is to minimize the number of packages you depend on.</span></span>

<span data-ttu-id="2600d-122">✔️ REVISE la biblioteca de .NET en busca de dependencias innecesarias.</span><span class="sxs-lookup"><span data-stu-id="2600d-122">✔️ DO review your .NET library for unnecessary dependencies.</span></span>

## <a name="nuget-dependency-version-ranges"></a><span data-ttu-id="2600d-123">Intervalos de versiones de dependencia de NuGet</span><span class="sxs-lookup"><span data-stu-id="2600d-123">NuGet dependency version ranges</span></span>

<span data-ttu-id="2600d-124">Una referencia de paquete especifica el intervalo de paquetes válidos que permite.</span><span class="sxs-lookup"><span data-stu-id="2600d-124">A package reference specifies the range of valid packages it allows.</span></span> <span data-ttu-id="2600d-125">Normalmente, la versión de referencia de paquete del archivo de proyecto es la versión mínima y no hay una máxima.</span><span class="sxs-lookup"><span data-stu-id="2600d-125">Typically, the package reference version in the project file is the minimum version and there's no maximum.</span></span>

```xml
<!-- Accepts any version 1.0 and above. -->
<PackageReference Include="ExamplePackage" Version="1.0" />
```

<span data-ttu-id="2600d-126">Las reglas que NuGet usa al resolver dependencias son [complejas](/nuget/consume-packages/dependency-resolution), pero NuGet siempre busca la versión aplicable más baja.</span><span class="sxs-lookup"><span data-stu-id="2600d-126">The rules that NuGet uses when resolving dependencies are [complex](/nuget/consume-packages/dependency-resolution), but NuGet always looks for the lowest applicable version.</span></span> <span data-ttu-id="2600d-127">NuGet prefiere la versión más baja aplicable en lugar de usar la más alta disponible porque la más baja tendrá los menores problemas de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2600d-127">NuGet prefers the lowest applicable version over using the highest available because the lowest will have the least compatibility issues.</span></span>

<span data-ttu-id="2600d-128">Debido a la regla de versión más baja aplicable de NuGet, no es necesario colocar una versión superior o un intervalo exacto en referencias de paquete para evitar la obtención de la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2600d-128">Because of NuGet's lowest applicable version rule, it isn't necessary to place an upper version or exact range on package references to avoid getting the latest version.</span></span> <span data-ttu-id="2600d-129">NuGet ya intenta encontrar la versión más compatible y más baja automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2600d-129">NuGet already tries to find the lowest, most compatible version for you.</span></span>

```xml
<!-- Accepts 1.0 up to 1.x, but not 2.0 and higher. -->
<PackageReference Include="ExamplePackage" Version="[1.0,2.0)" />

<!-- Accepts exactly 1.0. -->
<PackageReference Include="ExamplePackage" Version="[1.0]" />
```

<span data-ttu-id="2600d-130">Los límites de versión superiores provocarán que NuGet genere un error si hay un conflicto.</span><span class="sxs-lookup"><span data-stu-id="2600d-130">Upper version limits will cause NuGet to fail if there's a conflict.</span></span> <span data-ttu-id="2600d-131">Por ejemplo, una biblioteca acepta exactamente la versión 1.0 mientras otra biblioteca requiere la versión 2.0 o una superior.</span><span class="sxs-lookup"><span data-stu-id="2600d-131">For example, one library accepts exactly 1.0 while another library requires 2.0 or above.</span></span> <span data-ttu-id="2600d-132">Aunque se pueden haber introducido cambios importantes en la versión 2.0, una dependencia de versión con límite superior o estricta garantiza un error.</span><span class="sxs-lookup"><span data-stu-id="2600d-132">While breaking changes may have been introduced in version 2.0, a strict or upper limit version dependency guarantees an error.</span></span>

<span data-ttu-id="2600d-133">![Conflicto de dependencias de rombo](./media/dependencies/diamond-dependency-conflict.png "Conflicto de dependencias de rombo")</span><span class="sxs-lookup"><span data-stu-id="2600d-133">![Diamond dependency conflict](./media/dependencies/diamond-dependency-conflict.png "Diamond dependency conflict")</span></span>

<span data-ttu-id="2600d-134">❌ NO tenga referencias de paquetes NuGet sin versión mínima.</span><span class="sxs-lookup"><span data-stu-id="2600d-134">❌ DO NOT have NuGet package references with no minimum version.</span></span>

<span data-ttu-id="2600d-135">❌ EVITE las referencias de paquetes NuGet que exijan una versión exacta.</span><span class="sxs-lookup"><span data-stu-id="2600d-135">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="2600d-136">❌ EVITE las referencias de paquetes NuGet con un límite superior de versión.</span><span class="sxs-lookup"><span data-stu-id="2600d-136">❌ AVOID NuGet package references with a version upper limit.</span></span>

## <a name="nuget-shared-source-packages"></a><span data-ttu-id="2600d-137">Paquetes NuGet de código fuente compartido</span><span class="sxs-lookup"><span data-stu-id="2600d-137">NuGet shared source packages</span></span>

<span data-ttu-id="2600d-138">Una forma de reducir las dependencias externas de los paquetes NuGet es hacer referencia a paquetes de código fuente compartido.</span><span class="sxs-lookup"><span data-stu-id="2600d-138">One way to reduce external NuGet package dependencies is to reference shared source packages.</span></span> <span data-ttu-id="2600d-139">Un paquete de código fuente compartido contiene [archivos de código fuente](/nuget/reference/nuspec#including-content-files) que se incluyen en un proyecto al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2600d-139">A shared source package contains [source code files](/nuget/reference/nuspec#including-content-files) that are included in a project when referenced.</span></span> <span data-ttu-id="2600d-140">Dado que solo se incluyen los archivos de código fuente que se compilan con el resto del proyecto, no hay ninguna dependencia externa ni posibilidad de conflicto.</span><span class="sxs-lookup"><span data-stu-id="2600d-140">Because you're just including source code files that are compiled with the rest of your project, there's no external dependency and chance of conflict.</span></span>

<span data-ttu-id="2600d-141">Los paquetes de código fuente compartido son excelentes para incluir pequeños fragmentos de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2600d-141">Shared source packages are great for including small pieces of functionality.</span></span> <span data-ttu-id="2600d-142">Por ejemplo, un paquete de código fuente compartido de los métodos auxiliares para llamadas HTTP.</span><span class="sxs-lookup"><span data-stu-id="2600d-142">For example, a shared source package of helper methods for making HTTP calls.</span></span>

<span data-ttu-id="2600d-143">![Paquete de código fuente compartido](./media/dependencies/shared-source-package.png "Paquete de código fuente compartido")</span><span class="sxs-lookup"><span data-stu-id="2600d-143">![Shared source package](./media/dependencies/shared-source-package.png "Shared source package")</span></span>

```xml
<PackageReference Include="Microsoft.Extensions.Buffers.Testing.Sources" PrivateAssets="All" Version="1.0" />
```

<span data-ttu-id="2600d-144">![Proyecto de código fuente compartido](./media/dependencies/shared-source-project.png "Proyecto de código fuente compartido")</span><span class="sxs-lookup"><span data-stu-id="2600d-144">![Shared source project](./media/dependencies/shared-source-project.png "Shared source project")</span></span>

<span data-ttu-id="2600d-145">Los paquetes de código fuente compartido tienen algunas limitaciones.</span><span class="sxs-lookup"><span data-stu-id="2600d-145">Shared source packages have some limitations.</span></span> <span data-ttu-id="2600d-146">Solo `PackageReference` puede hacer referencia a ellos, por lo que los proyectos `packages.config` más antiguos se excluyen.</span><span class="sxs-lookup"><span data-stu-id="2600d-146">They can only be referenced by `PackageReference`, so older `packages.config` projects are excluded.</span></span> <span data-ttu-id="2600d-147">Asimismo, los paquetes de código fuente compartido solo resultan útiles para los proyectos con el mismo tipo de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="2600d-147">Also shared source packages are only usable by projects with the same language type.</span></span> <span data-ttu-id="2600d-148">Debido a estas limitaciones, los paquetes de código fuente compartido son útiles para compartir la funcionalidad dentro de un proyecto de código abierto.</span><span class="sxs-lookup"><span data-stu-id="2600d-148">Because of these limitations shared source packages are best used to share functionality within an open-source project.</span></span>

<span data-ttu-id="2600d-149">✔️ ES RECOMENDABLE hacer referencia a paquetes de código fuente compartido para partes internas pequeñas de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2600d-149">✔️ CONSIDER referencing shared source packages for small, internal pieces of functionality.</span></span>

<span data-ttu-id="2600d-150">✔️ ES RECOMENDABLE convertir el paquete en un paquete de código fuente compartido si proporciona partes internas pequeñas de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2600d-150">✔️ CONSIDER making your package a shared source package if it provides small, internal pieces of functionality.</span></span>

<span data-ttu-id="2600d-151">✔️ HAGA REFERENCIA a paquetes de código fuente compartido con `PrivateAssets="All"`.</span><span class="sxs-lookup"><span data-stu-id="2600d-151">✔️ DO reference shared source packages with `PrivateAssets="All"`.</span></span>

> <span data-ttu-id="2600d-152">Esta opción indica a NuGet que el paquete solamente se debe usar en tiempo de desarrollo y no se debe exponer como una dependencia pública.</span><span class="sxs-lookup"><span data-stu-id="2600d-152">This setting tells NuGet the package is only to be used at development time and shouldn't be exposed as a public dependency.</span></span>

<span data-ttu-id="2600d-153">❌ NO tenga tipos de paquete de código fuente compartido en la API pública.</span><span class="sxs-lookup"><span data-stu-id="2600d-153">❌ DO NOT have shared source package types in your public API.</span></span>

> <span data-ttu-id="2600d-154">Los tipos de código fuente compartido se compilan en el ensamblado de referencia y no se pueden intercambiar entre límites de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2600d-154">Shared source types are compiled into the referencing assembly and can't be exchanged across assembly boundaries.</span></span> <span data-ttu-id="2600d-155">Por ejemplo, un tipo `IRepository` de código fuente compartido en un proyecto es un tipo independiente del mismo `IRepository` de código fuente compartido en otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="2600d-155">For example, a shared-source `IRepository` type in one project is a separate type from the same shared-source `IRepository` in another project.</span></span> <span data-ttu-id="2600d-156">Los tipos de paquetes de código fuente compartido deben tener una visibilidad `internal`.</span><span class="sxs-lookup"><span data-stu-id="2600d-156">Types in shared source packages should have an `internal` visibility.</span></span>

<span data-ttu-id="2600d-157">❌ NO publique paquetes de código fuente compartido en NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="2600d-157">❌ DO NOT publish shared source packages to NuGet.org.</span></span>

> <span data-ttu-id="2600d-158">Los paquetes de código fuente compartido contienen código fuente y solo los pueden usar los proyectos con el mismo tipo de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="2600d-158">Shared source packages contain source code and can only be used by projects with the same language type.</span></span> <span data-ttu-id="2600d-159">Por ejemplo, una aplicación de F# no puede usar el paquete de código fuente compartido de C#.</span><span class="sxs-lookup"><span data-stu-id="2600d-159">For example, a C# shared source package cannot be used by an F# application.</span></span>
>
> <span data-ttu-id="2600d-160">Publique paquetes de código fuente compartido en una [fuente local o MyGet](./publish-nuget-package.md) para usarlos de forma interna en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2600d-160">Publish shared source packages to a [local feed or MyGet](./publish-nuget-package.md) to consume them internally within your project.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2600d-161">[Anterior](nuget.md)
>[Siguiente](sourcelink.md)</span><span class="sxs-lookup"><span data-stu-id="2600d-161">[Previous](nuget.md)
[Next](sourcelink.md)</span></span>
