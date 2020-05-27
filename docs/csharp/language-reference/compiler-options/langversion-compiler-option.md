---
title: -langversion (Opciones del compilador de C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802955"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="e6540-102">-langversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e6540-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="e6540-103">Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="e6540-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6540-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6540-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="e6540-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e6540-105">Arguments</span></span>

`option`

<span data-ttu-id="e6540-106">Valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="e6540-106">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="e6540-107">La versión de idioma predeterminada depende de la plataforma de destino de la aplicación y la versión del SDK o de Visual Studio instalada.</span><span class="sxs-lookup"><span data-stu-id="e6540-107">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="e6540-108">Estas reglas se definen en el artículo sobre la [configuración de la versión del lenguaje](../configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e6540-108">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6540-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6540-109">Remarks</span></span>

<span data-ttu-id="e6540-110">Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="e6540-110">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="e6540-111">Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **-langversion** no ofrece las funciones equivalentes de una versión anterior del compilador.</span><span class="sxs-lookup"><span data-stu-id="e6540-111">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="e6540-112">Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica.</span><span class="sxs-lookup"><span data-stu-id="e6540-112">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="e6540-113">Aunque las nuevas características necesitan definitivamente una nueva actualización del compilador que también se publica junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores mediante la inclusión de paquetes NuGet u otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="e6540-113">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="e6540-114">Independientemente de la configuración de **-langversion** que use, usa la versión actual de Common Language Runtime para crear el archivo .exe o .dll.</span><span class="sxs-lookup"><span data-stu-id="e6540-114">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="e6540-115">Una excepción son los ensamblados de confianza y [-moduleassemblyname (Opción del compilador de C#)](./moduleassemblyname-compiler-option.md), que funcionan en **-langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="e6540-115">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="e6540-116">Para obtener otras formas de especificar la versión del lenguaje C#, consulte el artículo [Selección de la versión del lenguaje C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="e6540-116">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="e6540-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6540-117">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e6540-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e6540-118">C# language specification</span></span>

| <span data-ttu-id="e6540-119">Versión</span><span class="sxs-lookup"><span data-stu-id="e6540-119">Version</span></span>          | <span data-ttu-id="e6540-120">Link</span><span class="sxs-lookup"><span data-stu-id="e6540-120">Link</span></span>                       | <span data-ttu-id="e6540-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6540-121">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="e6540-122">C# 7.0 y posterior</span><span class="sxs-lookup"><span data-stu-id="e6540-122">C# 7.0 and later</span></span> |                            | <span data-ttu-id="e6540-123">No está disponible actualmente</span><span class="sxs-lookup"><span data-stu-id="e6540-123">Not currently available</span></span>                                                 |
| <span data-ttu-id="e6540-124">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="e6540-124">C# 6.0</span></span>           | <span data-ttu-id="e6540-125">[Vínculo][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="e6540-125">[Link][csharp-6]</span></span>           | <span data-ttu-id="e6540-126">Versión 6 de la especificación del lenguaje C#, borrador no oficial: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="e6540-126">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="e6540-127">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="e6540-127">C# 5.0</span></span>           | <span data-ttu-id="e6540-128">[Descargar PDF][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="e6540-128">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="e6540-129">Norma ECMA-334 estándar, quinta edición</span><span class="sxs-lookup"><span data-stu-id="e6540-129">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="e6540-130">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="e6540-130">C# 3.0</span></span>           | <span data-ttu-id="e6540-131">[Decargar DOC][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="e6540-131">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="e6540-132">Especificación del lenguaje C#, versión 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e6540-132">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="e6540-133">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="e6540-133">C# 2.0</span></span>           | <span data-ttu-id="e6540-134">[Descargar PDF][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="e6540-134">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="e6540-135">Norma ECMA-334 estándar, cuarta edición</span><span class="sxs-lookup"><span data-stu-id="e6540-135">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="e6540-136">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="e6540-136">C# 1.2</span></span>           | <span data-ttu-id="e6540-137">[Decargar DOC][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="e6540-137">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="e6540-138">Especificación del lenguaje C#, versión 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e6540-138">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="e6540-139">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="e6540-139">C# 1.0</span></span>           | <span data-ttu-id="e6540-140">[Decargar DOC][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="e6540-140">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="e6540-141">Especificación del lenguaje C#, versión 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e6540-141">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="e6540-142">Versión del SDK mínima necesaria para admitir todas las características del lenguaje</span><span class="sxs-lookup"><span data-stu-id="e6540-142">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="e6540-143">En la tabla siguiente se enumeran las versiones mínimas del SDK con el compilador de C# que admite la versión del lenguaje correspondiente:</span><span class="sxs-lookup"><span data-stu-id="e6540-143">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="e6540-144">Versión de C#</span><span class="sxs-lookup"><span data-stu-id="e6540-144">C# version</span></span> | <span data-ttu-id="e6540-145">Versión mínima del SDK</span><span class="sxs-lookup"><span data-stu-id="e6540-145">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="e6540-146">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="e6540-146">C# 8.0</span></span>     | <span data-ttu-id="e6540-147">Microsoft Visual Studio/Build Tools 2019, versión 16.3 o SDK de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e6540-147">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="e6540-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="e6540-148">C# 7.3</span></span>     | <span data-ttu-id="e6540-149">Microsoft Visual Studio/Build Tools 2017, versión 15.7</span><span class="sxs-lookup"><span data-stu-id="e6540-149">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="e6540-150">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="e6540-150">C# 7.2</span></span>     | <span data-ttu-id="e6540-151">Microsoft Visual Studio/Build Tools 2017, versión 15.5</span><span class="sxs-lookup"><span data-stu-id="e6540-151">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="e6540-152">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="e6540-152">C# 7.1</span></span>     | <span data-ttu-id="e6540-153">Microsoft Visual Studio/Build Tools 2017, versión 15.3</span><span class="sxs-lookup"><span data-stu-id="e6540-153">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="e6540-154">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="e6540-154">C# 7.0</span></span>     | <span data-ttu-id="e6540-155">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="e6540-155">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="e6540-156">C# 6</span><span class="sxs-lookup"><span data-stu-id="e6540-156">C# 6</span></span>       | <span data-ttu-id="e6540-157">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="e6540-157">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="e6540-158">C# 5</span><span class="sxs-lookup"><span data-stu-id="e6540-158">C# 5</span></span>       | <span data-ttu-id="e6540-159">Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e6540-159">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="e6540-160">C# 4</span><span class="sxs-lookup"><span data-stu-id="e6540-160">C# 4</span></span>       | <span data-ttu-id="e6540-161">Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="e6540-161">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="e6540-162">C# 3</span><span class="sxs-lookup"><span data-stu-id="e6540-162">C# 3</span></span>       | <span data-ttu-id="e6540-163">Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="e6540-163">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="e6540-164">C# 2</span><span class="sxs-lookup"><span data-stu-id="e6540-164">C# 2</span></span>       | <span data-ttu-id="e6540-165">Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="e6540-165">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="e6540-166">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="e6540-166">C# 1.0/1.2</span></span> | <span data-ttu-id="e6540-167">Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="e6540-167">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="e6540-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6540-168">See also</span></span>

- [<span data-ttu-id="e6540-169">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e6540-169">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="e6540-170">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e6540-170">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
