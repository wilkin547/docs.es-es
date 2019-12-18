---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998802"
---

<span data-ttu-id="2a75a-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="2a75a-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="2a75a-102">**product**</span><span class="sxs-lookup"><span data-stu-id="2a75a-102">**product**</span></span>\
<span data-ttu-id="2a75a-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="2a75a-103">The type of .NET product to install.</span></span> <span data-ttu-id="2a75a-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="2a75a-104">Valid options are:</span></span>

  - <span data-ttu-id="2a75a-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="2a75a-105">dotnet</span></span>
  - <span data-ttu-id="2a75a-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="2a75a-106">aspnetcore</span></span>

- <span data-ttu-id="2a75a-107">**type**</span><span class="sxs-lookup"><span data-stu-id="2a75a-107">**type**</span></span>\
<span data-ttu-id="2a75a-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a75a-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="2a75a-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="2a75a-109">Valid options are:</span></span>

  - <span data-ttu-id="2a75a-110">sdk</span><span class="sxs-lookup"><span data-stu-id="2a75a-110">sdk</span></span>
  - <span data-ttu-id="2a75a-111">runtime</span><span class="sxs-lookup"><span data-stu-id="2a75a-111">runtime</span></span>

- <span data-ttu-id="2a75a-112">**version**</span><span class="sxs-lookup"><span data-stu-id="2a75a-112">**version**</span></span>\
<span data-ttu-id="2a75a-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="2a75a-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="2a75a-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="2a75a-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="2a75a-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a75a-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="2a75a-116">3.0</span><span class="sxs-lookup"><span data-stu-id="2a75a-116">3.0</span></span>
  - <span data-ttu-id="2a75a-117">2.2</span><span class="sxs-lookup"><span data-stu-id="2a75a-117">2.2</span></span>
  - <span data-ttu-id="2a75a-118">2.1</span><span class="sxs-lookup"><span data-stu-id="2a75a-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="2a75a-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2a75a-119">Examples</span></span>

- <span data-ttu-id="2a75a-120">Instalación del SDK de .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="2a75a-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="2a75a-121">Instalación del entorno de ejecución de ASP.NET Core 3.0: `aspnetcore-runtime-3.0`</span><span class="sxs-lookup"><span data-stu-id="2a75a-121">Install the ASP.NET Core 3.0 runtime: `aspnetcore-runtime-3.0`</span></span>
- <span data-ttu-id="2a75a-122">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="2a75a-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="2a75a-123">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="2a75a-123">Troubleshoot</span></span>

<span data-ttu-id="2a75a-124">Si la combinación de paquetes no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2a75a-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="2a75a-125">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2a75a-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="2a75a-126">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="2a75a-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
