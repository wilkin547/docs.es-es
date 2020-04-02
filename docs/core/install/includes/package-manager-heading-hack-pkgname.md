---
ms.openlocfilehash: 4340ed7444681b4601dea50c93926b0ee0c07eec
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134110"
---

<span data-ttu-id="4c384-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="4c384-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="4c384-102">**product**</span><span class="sxs-lookup"><span data-stu-id="4c384-102">**product**</span></span>\
<span data-ttu-id="4c384-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="4c384-103">The type of .NET product to install.</span></span> <span data-ttu-id="4c384-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="4c384-104">Valid options are:</span></span>

  - <span data-ttu-id="4c384-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="4c384-105">dotnet</span></span>
  - <span data-ttu-id="4c384-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="4c384-106">aspnetcore</span></span>

- <span data-ttu-id="4c384-107">**type**</span><span class="sxs-lookup"><span data-stu-id="4c384-107">**type**</span></span>\
<span data-ttu-id="4c384-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c384-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="4c384-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="4c384-109">Valid options are:</span></span>

  - <span data-ttu-id="4c384-110">sdk</span><span class="sxs-lookup"><span data-stu-id="4c384-110">sdk</span></span>
  - <span data-ttu-id="4c384-111">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4c384-111">runtime</span></span>

- <span data-ttu-id="4c384-112">**version**</span><span class="sxs-lookup"><span data-stu-id="4c384-112">**version**</span></span>\
<span data-ttu-id="4c384-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="4c384-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="4c384-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="4c384-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="4c384-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c384-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="4c384-116">3.1</span><span class="sxs-lookup"><span data-stu-id="4c384-116">3.1</span></span>
  - <span data-ttu-id="4c384-117">3.0</span><span class="sxs-lookup"><span data-stu-id="4c384-117">3.0</span></span>
  - <span data-ttu-id="4c384-118">2.1</span><span class="sxs-lookup"><span data-stu-id="4c384-118">2.1</span></span>

  <span data-ttu-id="4c384-119">Es posible que el SDK o el entorno de ejecución que intenta descargar no esté disponible para su distribución de Linux.</span><span class="sxs-lookup"><span data-stu-id="4c384-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="4c384-120">Para obtener una lista de las distribuciones admitidas, consulte [Dependencias y requisitos de .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="4c384-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="4c384-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4c384-121">Examples</span></span>

- <span data-ttu-id="4c384-122">Instalación del runtime de ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="4c384-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="4c384-123">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="4c384-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="4c384-124">Instalación del SDK de .NET Core 3.1: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="4c384-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="4c384-125">Falta el paquete</span><span class="sxs-lookup"><span data-stu-id="4c384-125">Package missing</span></span>

<span data-ttu-id="4c384-126">Si la combinación de paquete y versión no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4c384-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="4c384-127">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c384-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="4c384-128">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="4c384-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="4c384-129">Para obtener una lista de las distribuciones de Linux compatibles con .NET Core, consulte [Dependencias y requisitos de .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="4c384-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
