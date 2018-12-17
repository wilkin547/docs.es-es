---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128937"
---
# <a name="sourcelink"></a><span data-ttu-id="3b15d-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="3b15d-103">SourceLink</span></span>

<span data-ttu-id="3b15d-104">SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet.</span><span class="sxs-lookup"><span data-stu-id="3b15d-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="3b15d-105">SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete.</span><span class="sxs-lookup"><span data-stu-id="3b15d-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="3b15d-106">Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente.</span><span class="sxs-lookup"><span data-stu-id="3b15d-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="3b15d-107">SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="3b15d-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="3b15d-108">Demostración de SourceLink</span><span class="sxs-lookup"><span data-stu-id="3b15d-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="3b15d-109">Uso de SourceLink</span><span class="sxs-lookup"><span data-stu-id="3b15d-109">Using SourceLink</span></span>

<span data-ttu-id="3b15d-110">Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="3b15d-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="3b15d-111">Puede usar [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="3b15d-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="3b15d-112">Compruebe que los metadatos de `Repository` están presentes con un identificador de comentarios y que los archivos .pdb se encuentran con los .dll de cada destino.</span><span class="sxs-lookup"><span data-stu-id="3b15d-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="3b15d-113">![SourceLink en NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="3b15d-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="3b15d-114">**✔️ ES RECOMENDABLE** usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="3b15d-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="3b15d-115">Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.</span><span class="sxs-lookup"><span data-stu-id="3b15d-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="3b15d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="3b15d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="3b15d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.</span><span class="sxs-lookup"><span data-stu-id="3b15d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="3b15d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="3b15d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="3b15d-119">**✔️ ES RECOMENDABLE** incluir los archivos de símbolos (`*.pdb`) en el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="3b15d-119">**✔️ CONSIDER** including symbol files (`*.pdb`) in the NuGet package.</span></span>

> <span data-ttu-id="3b15d-120">Normalmente, publicaría los archivos de símbolos en un [paquete de símbolos](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="3b15d-120">Ordinarily, you'd publish symbol files in a [symbol package](./nuget.md#symbol-packages).</span></span> <span data-ttu-id="3b15d-121">Actualmente el host público principal para paquetes de símbolos no es compatible con los archivos de símbolos portátiles (`*.pdb`) creados por los proyectos estilo de SDK, y los paquetes de símbolos no son útiles.</span><span class="sxs-lookup"><span data-stu-id="3b15d-121">Currently the main public host for symbol packages doesn't support the portable symbol files (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3b15d-122">[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="3b15d-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>