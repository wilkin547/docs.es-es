---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 3d768ae6e79efa23a8402ea37bc34cd58cd52c8c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744539"
---
# <a name="source-link"></a><span data-ttu-id="462fe-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="462fe-103">Source Link</span></span>

<span data-ttu-id="462fe-104">SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet.</span><span class="sxs-lookup"><span data-stu-id="462fe-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="462fe-105">SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete.</span><span class="sxs-lookup"><span data-stu-id="462fe-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="462fe-106">Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente.</span><span class="sxs-lookup"><span data-stu-id="462fe-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="462fe-107">SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="462fe-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="462fe-108">Demostración de SourceLink</span><span class="sxs-lookup"><span data-stu-id="462fe-108">Source Link demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="462fe-109">Uso de SourceLink</span><span class="sxs-lookup"><span data-stu-id="462fe-109">Using Source Link</span></span>

<span data-ttu-id="462fe-110">Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="462fe-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="462fe-111">Puede usar el [Explorador de paquetes NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="462fe-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="462fe-112">Compruebe que los metadatos de `Repository` están presentes con un identificador de la confirmación y que los archivos .pdb se encuentran con los .dll de cada destino.</span><span class="sxs-lookup"><span data-stu-id="462fe-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="462fe-113">![SourceLink en el explorador de paquetes NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink en el explorador de paquetes NuGet")</span><span class="sxs-lookup"><span data-stu-id="462fe-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="462fe-114">✔️ ES RECOMENDABLE usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="462fe-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="462fe-115">Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.</span><span class="sxs-lookup"><span data-stu-id="462fe-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="462fe-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="462fe-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="462fe-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.</span><span class="sxs-lookup"><span data-stu-id="462fe-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="462fe-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="462fe-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="462fe-119">✔️ ES RECOMENDABLE publicar archivos de símbolos (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="462fe-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="462fe-120">Para obtener la mejor experiencia de depuración, la biblioteca debe publicar archivos de símbolos, además de usar SourceLink.</span><span class="sxs-lookup"><span data-stu-id="462fe-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="462fe-121">Para más información sobre los archivos de símbolos y los paquetes de símbolos, consulte [Paquetes de símbolos](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="462fe-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="462fe-122">[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="462fe-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
