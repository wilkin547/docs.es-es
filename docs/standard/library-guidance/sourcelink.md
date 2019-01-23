---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: be97f868e2fcfc6c45e4bbac45b033f8914f4d99
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333543"
---
# <a name="sourcelink"></a><span data-ttu-id="d09b0-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="d09b0-103">SourceLink</span></span>

<span data-ttu-id="d09b0-104">SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet.</span><span class="sxs-lookup"><span data-stu-id="d09b0-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="d09b0-105">SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete.</span><span class="sxs-lookup"><span data-stu-id="d09b0-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="d09b0-106">Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente.</span><span class="sxs-lookup"><span data-stu-id="d09b0-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="d09b0-107">SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="d09b0-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="d09b0-108">Demostración de SourceLink</span><span class="sxs-lookup"><span data-stu-id="d09b0-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="d09b0-109">Uso de SourceLink</span><span class="sxs-lookup"><span data-stu-id="d09b0-109">Using SourceLink</span></span>

<span data-ttu-id="d09b0-110">Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="d09b0-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="d09b0-111">Puede usar [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="d09b0-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="d09b0-112">Compruebe que los metadatos de `Repository` están presentes con un identificador de comentarios y que los archivos .pdb se encuentran con los .dll de cada destino.</span><span class="sxs-lookup"><span data-stu-id="d09b0-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="d09b0-113">![SourceLink en NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="d09b0-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="d09b0-114">**✔️ ES RECOMENDABLE** usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="d09b0-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="d09b0-115">Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.</span><span class="sxs-lookup"><span data-stu-id="d09b0-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="d09b0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="d09b0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="d09b0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.</span><span class="sxs-lookup"><span data-stu-id="d09b0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="d09b0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="d09b0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="d09b0-119">**✔️ CONSIDERE LA POSIBILIDAD DE** publicar archivos de símbolos (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="d09b0-119">**✔️ CONSIDER** publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="d09b0-120">Para más información sobre los archivos de símbolos y los paquetes de símbolos, consulte [Paquetes de símbolos](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="d09b0-120">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d09b0-121">[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="d09b0-121">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
