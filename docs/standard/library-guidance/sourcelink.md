---
title: Bibliotecas de .NET y de SourceLink
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370316"
---
# <a name="sourcelink"></a><span data-ttu-id="2490a-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="2490a-103">SourceLink</span></span>

<span data-ttu-id="2490a-104">SourceLink es una tecnología que permite depurar el código fuente de los ensamblados de .NET de NuGet por desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="2490a-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="2490a-105">SourceLink ejecuta al crear el paquete de NuGet y las incrusta los metadatos de control de código fuente dentro de los ensamblados y el paquete.</span><span class="sxs-lookup"><span data-stu-id="2490a-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="2490a-106">Los desarrolladores que descargue el paquete y dispondrá de SourceLink habilitado en Visual Studio pueden entrar en su código fuente.</span><span class="sxs-lookup"><span data-stu-id="2490a-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="2490a-107">SourceLink proporciona los metadatos de control de origen para crear una excelente experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="2490a-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="2490a-108">Demostración de SourceLink</span><span class="sxs-lookup"><span data-stu-id="2490a-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="2490a-109">Uso de SourceLink</span><span class="sxs-lookup"><span data-stu-id="2490a-109">Using SourceLink</span></span>

<span data-ttu-id="2490a-110">Puede encontrar instrucciones para el uso de SourceLink en el [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2490a-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="2490a-111">Puede usar [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se ha insertado correctamente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="2490a-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="2490a-112">Compruebe el `Repository` metadatos están presente con un identificador de comentario y que los archivos .pdb se encuentran con DLL de cada destino.</span><span class="sxs-lookup"><span data-stu-id="2490a-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="2490a-113">![SourceLink en el Explorador de paquetes de NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink en el Explorador de paquetes de NuGet")</span><span class="sxs-lookup"><span data-stu-id="2490a-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="2490a-114">**Considere la posibilidad de ✔️** con SourceLink para agregar metadatos de control de origen a los ensamblados y paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="2490a-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

<span data-ttu-id="2490a-115">**Considere la posibilidad de ✔️** incluyendo archivos PDB en el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="2490a-115">**✔️ CONSIDER** including PDB files in the NuGet package.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2490a-116">[Anterior](./dependencies.md)
[Siguiente](./publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="2490a-116">[Previous](./dependencies.md)
[Next](./publish-nuget-package.md)</span></span>
