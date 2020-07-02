---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620584"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="6448d-101">La ausencia de moniker de la plataforma de destino da lugar a un comportamiento de la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="6448d-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="6448d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6448d-102">Details</span></span>

<span data-ttu-id="6448d-103">Las aplicaciones sin un elemento <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> aplicado en el nivel de ensamblado se ejecutarán automáticamente con la semántica (las peculiaridades) de .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="6448d-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="6448d-104">Para garantizar una buena calidad, se recomienda que todos los archivos binarios incluyan un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> explícito en el que se indique la versión de .NET Framework con la que se compilaron.</span><span class="sxs-lookup"><span data-stu-id="6448d-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="6448d-105">Tenga en cuenta que usar un moniker de la plataforma de destino en un archivo de proyecto hará que MSBuild aplique automáticamente un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6448d-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6448d-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6448d-106">Suggestion</span></span>

<span data-ttu-id="6448d-107">Se debe proporcionar un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, agregándolo directamente al ensamblado o especificando una plataforma de destino en el [archivo de proyecto, o bien a través de la GUI de propiedades del proyecto de Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span><span class="sxs-lookup"><span data-stu-id="6448d-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="6448d-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6448d-108">Name</span></span>    | <span data-ttu-id="6448d-109">Valor</span><span class="sxs-lookup"><span data-stu-id="6448d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6448d-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6448d-110">Scope</span></span>   |<span data-ttu-id="6448d-111">Major</span><span class="sxs-lookup"><span data-stu-id="6448d-111">Major</span></span>|
|<span data-ttu-id="6448d-112">Versión</span><span class="sxs-lookup"><span data-stu-id="6448d-112">Version</span></span>|<span data-ttu-id="6448d-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6448d-113">4.5</span></span>|
|<span data-ttu-id="6448d-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="6448d-114">Type</span></span>|<span data-ttu-id="6448d-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6448d-115">Runtime</span></span>|
