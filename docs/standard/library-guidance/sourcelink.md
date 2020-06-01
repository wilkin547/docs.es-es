---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 5dee2a6b1f77daa641351e02c1dd3e0a38f66550
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201983"
---
# <a name="source-link"></a><span data-ttu-id="6b01b-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="6b01b-103">Source Link</span></span>

<span data-ttu-id="6b01b-104">SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet.</span><span class="sxs-lookup"><span data-stu-id="6b01b-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="6b01b-105">SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete.</span><span class="sxs-lookup"><span data-stu-id="6b01b-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="6b01b-106">Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente.</span><span class="sxs-lookup"><span data-stu-id="6b01b-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="6b01b-107">SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="6b01b-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="6b01b-108">Demostración de SourceLink</span><span class="sxs-lookup"><span data-stu-id="6b01b-108">Source Link demo</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="6b01b-109">Uso de SourceLink</span><span class="sxs-lookup"><span data-stu-id="6b01b-109">Using Source Link</span></span>

<span data-ttu-id="6b01b-110">Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="6b01b-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="6b01b-111">Puede usar el [Explorador de paquetes NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="6b01b-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="6b01b-112">Compruebe que los metadatos de `Repository` están presentes con un identificador de la confirmación y que los archivos .pdb se encuentran con los .dll de cada destino.</span><span class="sxs-lookup"><span data-stu-id="6b01b-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="6b01b-113">![SourceLink en el explorador de paquetes NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink en el explorador de paquetes NuGet")</span><span class="sxs-lookup"><span data-stu-id="6b01b-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="6b01b-114">✔️ ES RECOMENDABLE usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="6b01b-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="6b01b-115">Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.</span><span class="sxs-lookup"><span data-stu-id="6b01b-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="6b01b-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="6b01b-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="6b01b-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.</span><span class="sxs-lookup"><span data-stu-id="6b01b-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="6b01b-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="6b01b-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="6b01b-119">✔️ ES RECOMENDABLE publicar archivos de símbolos (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="6b01b-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="6b01b-120">Para obtener la mejor experiencia de depuración, la biblioteca debe publicar archivos de símbolos, además de usar SourceLink.</span><span class="sxs-lookup"><span data-stu-id="6b01b-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="6b01b-121">Para más información sobre los archivos de símbolos y los paquetes de símbolos, consulte [Paquetes de símbolos](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="6b01b-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

<span data-ttu-id="6b01b-122">✔️ CONSIDERE la posibilidad de habilitar compilaciones deterministas.</span><span class="sxs-lookup"><span data-stu-id="6b01b-122">✔️ CONSIDER enabling deterministic builds.</span></span>

> <span data-ttu-id="6b01b-123">Las compilaciones deterministas permiten comprobar que el binario resultante se compiló a partir del origen especificado y proporcionan trazabilidad.</span><span class="sxs-lookup"><span data-stu-id="6b01b-123">Deterministic builds enable verification that the resulting binary was built from the specified source and provide traceability.</span></span> <span data-ttu-id="6b01b-124">Para más información sobre las compilaciones deterministas y las instrucciones para habilitarlas, consulte [Compilaciones deterministas](https://github.com/clairernovotny/DeterministicBuilds).</span><span class="sxs-lookup"><span data-stu-id="6b01b-124">For more information about deterministic builds and instructions for enabling them, see [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6b01b-125">[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="6b01b-125">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
