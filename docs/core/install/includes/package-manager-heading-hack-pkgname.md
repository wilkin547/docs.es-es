---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116155"
---

<span data-ttu-id="e19f4-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="e19f4-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="e19f4-102">**product**</span><span class="sxs-lookup"><span data-stu-id="e19f4-102">**product**</span></span>\
<span data-ttu-id="e19f4-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="e19f4-103">The type of .NET product to install.</span></span> <span data-ttu-id="e19f4-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="e19f4-104">Valid options are:</span></span>

  - <span data-ttu-id="e19f4-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="e19f4-105">dotnet</span></span>
  - <span data-ttu-id="e19f4-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="e19f4-106">aspnetcore</span></span>

- <span data-ttu-id="e19f4-107">**type**</span><span class="sxs-lookup"><span data-stu-id="e19f4-107">**type**</span></span>\
<span data-ttu-id="e19f4-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e19f4-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="e19f4-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="e19f4-109">Valid options are:</span></span>

  - <span data-ttu-id="e19f4-110">sdk</span><span class="sxs-lookup"><span data-stu-id="e19f4-110">sdk</span></span>
  - <span data-ttu-id="e19f4-111">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e19f4-111">runtime</span></span>

- <span data-ttu-id="e19f4-112">**version**</span><span class="sxs-lookup"><span data-stu-id="e19f4-112">**version**</span></span>\
<span data-ttu-id="e19f4-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="e19f4-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="e19f4-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="e19f4-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="e19f4-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e19f4-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="e19f4-116">3.0</span><span class="sxs-lookup"><span data-stu-id="e19f4-116">3.0</span></span>
  - <span data-ttu-id="e19f4-117">2.2</span><span class="sxs-lookup"><span data-stu-id="e19f4-117">2.2</span></span>
  - <span data-ttu-id="e19f4-118">2.1</span><span class="sxs-lookup"><span data-stu-id="e19f4-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="e19f4-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e19f4-119">Examples</span></span>

- <span data-ttu-id="e19f4-120">Instalación del SDK de .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="e19f4-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="e19f4-121">Instalación del runtime de ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="e19f4-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="e19f4-122">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="e19f4-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="e19f4-123">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="e19f4-123">Troubleshoot</span></span>

<span data-ttu-id="e19f4-124">Si la combinación de paquetes no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="e19f4-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="e19f4-125">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e19f4-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="e19f4-126">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="e19f4-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
