---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77466061"
---

<span data-ttu-id="1c296-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="1c296-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="1c296-102">**product**</span><span class="sxs-lookup"><span data-stu-id="1c296-102">**product**</span></span>\
<span data-ttu-id="1c296-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="1c296-103">The type of .NET product to install.</span></span> <span data-ttu-id="1c296-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="1c296-104">Valid options are:</span></span>

  - <span data-ttu-id="1c296-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="1c296-105">dotnet</span></span>
  - <span data-ttu-id="1c296-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="1c296-106">aspnetcore</span></span>

- <span data-ttu-id="1c296-107">**type**</span><span class="sxs-lookup"><span data-stu-id="1c296-107">**type**</span></span>\
<span data-ttu-id="1c296-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c296-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="1c296-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="1c296-109">Valid options are:</span></span>

  - <span data-ttu-id="1c296-110">sdk</span><span class="sxs-lookup"><span data-stu-id="1c296-110">sdk</span></span>
  - <span data-ttu-id="1c296-111">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1c296-111">runtime</span></span>

- <span data-ttu-id="1c296-112">**version**</span><span class="sxs-lookup"><span data-stu-id="1c296-112">**version**</span></span>\
<span data-ttu-id="1c296-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="1c296-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="1c296-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="1c296-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="1c296-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c296-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="1c296-116">3.1</span><span class="sxs-lookup"><span data-stu-id="1c296-116">3.1</span></span>
  - <span data-ttu-id="1c296-117">3.0</span><span class="sxs-lookup"><span data-stu-id="1c296-117">3.0</span></span>
  - <span data-ttu-id="1c296-118">2.1</span><span class="sxs-lookup"><span data-stu-id="1c296-118">2.1</span></span>

  <span data-ttu-id="1c296-119">Es posible que el SDK o el entorno de ejecución que intenta descargar no esté disponible para su distribución de Linux.</span><span class="sxs-lookup"><span data-stu-id="1c296-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="1c296-120">Para obtener una lista de las distribuciones admitidas, consulte [Dependencias y requisitos de .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="1c296-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="1c296-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1c296-121">Examples</span></span>

- <span data-ttu-id="1c296-122">Instalación del runtime de ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="1c296-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="1c296-123">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="1c296-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="1c296-124">Instalación del SDK de .NET Core 3.0: `dotnet-sdk-3.0`</span><span class="sxs-lookup"><span data-stu-id="1c296-124">Install the .NET Core 3.0 SDK: `dotnet-sdk-3.0`</span></span>

### <a name="package-missing"></a><span data-ttu-id="1c296-125">Falta el paquete</span><span class="sxs-lookup"><span data-stu-id="1c296-125">Package missing</span></span>

<span data-ttu-id="1c296-126">Si la combinación de paquete y versión no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1c296-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="1c296-127">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c296-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="1c296-128">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="1c296-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="1c296-129">Para obtener una lista de las distribuciones de Linux compatibles con .NET Core, consulte [Dependencias y requisitos de .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="1c296-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
