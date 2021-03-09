---
description: -langversion (Opciones del compilador de C#)
title: -langversion (Opciones del compilador de C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 987177cc203b4c6202e8c14d8a9f4b41721e836f
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104879"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="04ae9-103">-langversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="04ae9-103">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="04ae9-104">Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="04ae9-104">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="04ae9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04ae9-105">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="04ae9-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="04ae9-106">Arguments</span></span>

`option`

<span data-ttu-id="04ae9-107">Valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="04ae9-107">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="04ae9-108">La versión de idioma predeterminada depende de la plataforma de destino de la aplicación y la versión del SDK o de Visual Studio instalada.</span><span class="sxs-lookup"><span data-stu-id="04ae9-108">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="04ae9-109">Estas reglas se definen en el artículo sobre la [configuración de la versión del lenguaje](../configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="04ae9-109">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="04ae9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04ae9-110">Remarks</span></span>

<span data-ttu-id="04ae9-111">Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="04ae9-111">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="04ae9-112">Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **-langversion** no ofrece las funciones equivalentes de una versión anterior del compilador.</span><span class="sxs-lookup"><span data-stu-id="04ae9-112">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="04ae9-113">Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica.</span><span class="sxs-lookup"><span data-stu-id="04ae9-113">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="04ae9-114">Aunque las nuevas características necesitan definitivamente una nueva actualización del compilador que también se publica junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores mediante la inclusión de paquetes NuGet u otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="04ae9-114">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="04ae9-115">Independientemente de la configuración de **-langversion** que use, usa la versión actual de Common Language Runtime para crear el archivo .exe o .dll.</span><span class="sxs-lookup"><span data-stu-id="04ae9-115">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="04ae9-116">Una excepción son los ensamblados de confianza y [-moduleassemblyname (Opción del compilador de C#)](./moduleassemblyname-compiler-option.md), que funcionan en **-langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="04ae9-116">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="04ae9-117">Para obtener otras formas de especificar la versión del lenguaje C#, consulte el artículo [Selección de la versión del lenguaje C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="04ae9-117">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="04ae9-118">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="04ae9-118">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="04ae9-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="04ae9-119">C# language specification</span></span>

| <span data-ttu-id="04ae9-120">Versión</span><span class="sxs-lookup"><span data-stu-id="04ae9-120">Version</span></span>          | <span data-ttu-id="04ae9-121">Vínculo</span><span class="sxs-lookup"><span data-stu-id="04ae9-121">Link</span></span>                       | <span data-ttu-id="04ae9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ae9-122">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="04ae9-123">C# 7.0 y posterior</span><span class="sxs-lookup"><span data-stu-id="04ae9-123">C# 7.0 and later</span></span> |                            | <span data-ttu-id="04ae9-124">No está disponible actualmente</span><span class="sxs-lookup"><span data-stu-id="04ae9-124">Not currently available</span></span>                                                 |
| <span data-ttu-id="04ae9-125">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-125">C# 6.0</span></span>           | <span data-ttu-id="04ae9-126">[Vínculo][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="04ae9-126">[Link][csharp-6]</span></span>           | <span data-ttu-id="04ae9-127">Versión 6 de la especificación del lenguaje C#, borrador no oficial: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="04ae9-127">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="04ae9-128">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-128">C# 5.0</span></span>           | <span data-ttu-id="04ae9-129">[Descargar PDF][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="04ae9-129">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="04ae9-130">Norma ECMA-334 estándar, quinta edición</span><span class="sxs-lookup"><span data-stu-id="04ae9-130">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="04ae9-131">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-131">C# 3.0</span></span>           | <span data-ttu-id="04ae9-132">[Decargar DOC][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="04ae9-132">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="04ae9-133">Especificación del lenguaje C#, versión 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="04ae9-133">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="04ae9-134">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-134">C# 2.0</span></span>           | <span data-ttu-id="04ae9-135">[Descargar PDF][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="04ae9-135">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="04ae9-136">Norma ECMA-334 estándar, cuarta edición</span><span class="sxs-lookup"><span data-stu-id="04ae9-136">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="04ae9-137">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="04ae9-137">C# 1.2</span></span>           | <span data-ttu-id="04ae9-138">[Decargar DOC][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="04ae9-138">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="04ae9-139">Especificación del lenguaje C#, versión 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="04ae9-139">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="04ae9-140">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-140">C# 1.0</span></span>           | <span data-ttu-id="04ae9-141">[Decargar DOC][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="04ae9-141">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="04ae9-142">Especificación del lenguaje C#, versión 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="04ae9-142">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_5th_edition_december_2017.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_4th_edition_june_2006.pdf
[csharp-1.2]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_2nd_edition_december_2002.pdf
[csharp-1]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_1st_edition_december_2001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="04ae9-143">Versión del SDK mínima necesaria para admitir todas las características del lenguaje</span><span class="sxs-lookup"><span data-stu-id="04ae9-143">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="04ae9-144">En la tabla siguiente se enumeran las versiones mínimas del SDK con el compilador de C# que admite la versión del lenguaje correspondiente:</span><span class="sxs-lookup"><span data-stu-id="04ae9-144">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="04ae9-145">Versión de C#</span><span class="sxs-lookup"><span data-stu-id="04ae9-145">C# version</span></span> | <span data-ttu-id="04ae9-146">Versión mínima del SDK</span><span class="sxs-lookup"><span data-stu-id="04ae9-146">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="04ae9-147">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-147">C# 8.0</span></span>     | <span data-ttu-id="04ae9-148">Microsoft Visual Studio/Build Tools 2019, versión 16.3 o SDK de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-148">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="04ae9-149">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="04ae9-149">C# 7.3</span></span>     | <span data-ttu-id="04ae9-150">Microsoft Visual Studio/Build Tools 2017, versión 15.7</span><span class="sxs-lookup"><span data-stu-id="04ae9-150">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="04ae9-151">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="04ae9-151">C# 7.2</span></span>     | <span data-ttu-id="04ae9-152">Microsoft Visual Studio/Build Tools 2017, versión 15.5</span><span class="sxs-lookup"><span data-stu-id="04ae9-152">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="04ae9-153">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="04ae9-153">C# 7.1</span></span>     | <span data-ttu-id="04ae9-154">Microsoft Visual Studio/Build Tools 2017, versión 15.3</span><span class="sxs-lookup"><span data-stu-id="04ae9-154">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="04ae9-155">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-155">C# 7.0</span></span>     | <span data-ttu-id="04ae9-156">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="04ae9-156">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="04ae9-157">C# 6</span><span class="sxs-lookup"><span data-stu-id="04ae9-157">C# 6</span></span>       | <span data-ttu-id="04ae9-158">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="04ae9-158">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="04ae9-159">C# 5</span><span class="sxs-lookup"><span data-stu-id="04ae9-159">C# 5</span></span>       | <span data-ttu-id="04ae9-160">Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="04ae9-160">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="04ae9-161">C# 4</span><span class="sxs-lookup"><span data-stu-id="04ae9-161">C# 4</span></span>       | <span data-ttu-id="04ae9-162">Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-162">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="04ae9-163">C# 3</span><span class="sxs-lookup"><span data-stu-id="04ae9-163">C# 3</span></span>       | <span data-ttu-id="04ae9-164">Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="04ae9-164">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="04ae9-165">C# 2</span><span class="sxs-lookup"><span data-stu-id="04ae9-165">C# 2</span></span>       | <span data-ttu-id="04ae9-166">Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-166">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="04ae9-167">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="04ae9-167">C# 1.0/1.2</span></span> | <span data-ttu-id="04ae9-168">Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="04ae9-168">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="04ae9-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="04ae9-169">See also</span></span>

- [<span data-ttu-id="04ae9-170">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="04ae9-170">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="04ae9-171">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="04ae9-171">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
