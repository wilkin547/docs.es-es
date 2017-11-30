---
title: "Cómo administrar las versiones de dependencias de paquete para .NET Core 1.0"
description: "Obtenga información sobre la administración de versiones de dependencias de paquete para aplicaciones y bibliotecas de .NET Core."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.openlocfilehash: b0d4082d020da782b334a5b3999905f7de744e64
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2017
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="df7d8-104">Cómo administrar las versiones de dependencias de paquete para .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="df7d8-104">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="df7d8-105">En este artículo se analiza lo que debe saber sobre las versiones de paquete para las bibliotecas y aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df7d8-105">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="df7d8-106">Glosario</span><span class="sxs-lookup"><span data-stu-id="df7d8-106">Glossary</span></span>

<span data-ttu-id="df7d8-107">**Corrección**: corregir las dependencias significa que usa la misma "familia" de paquetes lanzada en NuGet para .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-107">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="df7d8-108">**Metapaquete**: un paquete NuGet que representa un conjunto de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="df7d8-108">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="df7d8-109">**Recorte**: acción de quitar de un metapaquete los paquetes de los cuales no depende.</span><span class="sxs-lookup"><span data-stu-id="df7d8-109">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="df7d8-110">Es importante para los creadores de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="df7d8-110">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="df7d8-111">Consulte [Reducción de dependencias de paquete con project.json](../deploying/reducing-dependencies.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="df7d8-111">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="df7d8-112">Corrección de las dependencias a .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="df7d8-112">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="df7d8-113">Para restaurar de forma fiable los paquetes y escribir código confiable, es importante que corrija las dependencias a las versiones de los paquetes incluidos con .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-113">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="df7d8-114">Esto significa que cada paquete debe tener una versión única sin calificadores adicionales.</span><span class="sxs-lookup"><span data-stu-id="df7d8-114">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="df7d8-115">**Ejemplos de paquetes corregidos a 1.0**</span><span class="sxs-lookup"><span data-stu-id="df7d8-115">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="df7d8-116">**Ejemplos de paquetes NO corregidos a 1.0**</span><span class="sxs-lookup"><span data-stu-id="df7d8-116">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="df7d8-117">¿Por qué es importante?</span><span class="sxs-lookup"><span data-stu-id="df7d8-117">Why does this matter?</span></span>

<span data-ttu-id="df7d8-118">Garantizamos que si corrige las dependencias para qué se distribuye junto con .NET Core 1.0, esos paquetes todos funcionan juntas.</span><span class="sxs-lookup"><span data-stu-id="df7d8-118">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="df7d8-119">Dicha garantía no existe si usa paquetes no corregidos de esa manera.</span><span class="sxs-lookup"><span data-stu-id="df7d8-119">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="df7d8-120">Escenarios</span><span class="sxs-lookup"><span data-stu-id="df7d8-120">Scenarios</span></span>

<span data-ttu-id="df7d8-121">A pesar de que hay una gran lista de todos los paquetes y sus versiones lanzadas con .NET Core 1.0, puede que no sea necesario consultarla si el código que tiene se encuentra en ciertos escenarios.</span><span class="sxs-lookup"><span data-stu-id="df7d8-121">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="df7d8-122">**¿Depende solo de** `NETStandard.Library`**?**</span><span class="sxs-lookup"><span data-stu-id="df7d8-122">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="df7d8-123">Si por lo tanto, debe corregir la `NETStandard.Library` paquete a la versión `1.6`.</span><span class="sxs-lookup"><span data-stu-id="df7d8-123">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="df7d8-124">Como se trata de un metapaquete mantenido, la clausura de su paquete también se corrige a 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-124">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="df7d8-125">**¿Depende solo de** `Microsoft.NETCore.App`**?**</span><span class="sxs-lookup"><span data-stu-id="df7d8-125">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="df7d8-126">Si por lo tanto, debe corregir la `Microsoft.NETCore.App` paquete a la versión `1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="df7d8-126">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="df7d8-127">Como se trata de un metapaquete mantenido, la clausura de su paquete también se corrige a 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-127">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="df7d8-128">**¿[Recorta](../deploying/reducing-dependencies.md) las dependencias del metapaquete** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**</span><span class="sxs-lookup"><span data-stu-id="df7d8-128">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="df7d8-129">Si es así, debe asegurarse de que el metapaquete con el que comienza esté corregido a 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-129">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="df7d8-130">Los paquetes individuales de los que depende después del recorte también se corrigen a 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-130">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="df7d8-131">**¿Depende de paquetes externos al metapaquete** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**</span><span class="sxs-lookup"><span data-stu-id="df7d8-131">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="df7d8-132">Si es así, debe corregir las otras dependencias a 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-132">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="df7d8-133">Consulte las versiones de paquete y los números de compilación correctos al final de este artículo.</span><span class="sxs-lookup"><span data-stu-id="df7d8-133">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="df7d8-134">Nota sobre el uso de una cadena con asterisco (\*) cuando cree versiones</span><span class="sxs-lookup"><span data-stu-id="df7d8-134">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="df7d8-135">Puede que haya adoptado un patrón de creación de versiones que usa una cadena con asterisco (\*) como la siguiente: `"System.Collections":"4.0.11-*"`.</span><span class="sxs-lookup"><span data-stu-id="df7d8-135">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="df7d8-136">**No debe hacer esto**.</span><span class="sxs-lookup"><span data-stu-id="df7d8-136">**You should not do this**.</span></span>  <span data-ttu-id="df7d8-137">Si usa la cadena con asterisco podría restaurar paquetes de distintas compilaciones, algunas de las cuales podrían ir mucho más allá de .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="df7d8-137">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="df7d8-138">Esto podría hacer que algunos paquetes no sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="df7d8-138">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="df7d8-139">Número de versión y paquetes organizados por metapaquete</span><span class="sxs-lookup"><span data-stu-id="df7d8-139">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="df7d8-140">[Lista de todos los paquetes del estándar .NET y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="df7d8-140">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="df7d8-141">[Lista de todos los paquetes de entorno de ejecución y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="df7d8-141">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="df7d8-142">[Lista de todos los paquetes de aplicaciones de .NET Core y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="df7d8-142">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
