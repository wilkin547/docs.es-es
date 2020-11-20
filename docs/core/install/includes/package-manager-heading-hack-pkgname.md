---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506883"
---

<span data-ttu-id="f3f6d-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="f3f6d-102">**product**</span><span class="sxs-lookup"><span data-stu-id="f3f6d-102">**product**</span></span>\
<span data-ttu-id="f3f6d-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-103">The type of .NET product to install.</span></span> <span data-ttu-id="f3f6d-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="f3f6d-104">Valid options are:</span></span>

  - <span data-ttu-id="f3f6d-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="f3f6d-105">dotnet</span></span>
  - <span data-ttu-id="f3f6d-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="f3f6d-106">aspnetcore</span></span>

- <span data-ttu-id="f3f6d-107">**type**</span><span class="sxs-lookup"><span data-stu-id="f3f6d-107">**type**</span></span>\
<span data-ttu-id="f3f6d-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="f3f6d-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="f3f6d-109">Valid options are:</span></span>

  - <span data-ttu-id="f3f6d-110">sdk</span><span class="sxs-lookup"><span data-stu-id="f3f6d-110">sdk</span></span>
  - <span data-ttu-id="f3f6d-111">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f3f6d-111">runtime</span></span>

- <span data-ttu-id="f3f6d-112">**version**</span><span class="sxs-lookup"><span data-stu-id="f3f6d-112">**version**</span></span>\
<span data-ttu-id="f3f6d-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="f3f6d-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="f3f6d-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3f6d-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="f3f6d-116">5.0</span><span class="sxs-lookup"><span data-stu-id="f3f6d-116">5.0</span></span>
  - <span data-ttu-id="f3f6d-117">3.1</span><span class="sxs-lookup"><span data-stu-id="f3f6d-117">3.1</span></span>
  - <span data-ttu-id="f3f6d-118">3.0</span><span class="sxs-lookup"><span data-stu-id="f3f6d-118">3.0</span></span>
  - <span data-ttu-id="f3f6d-119">2.1</span><span class="sxs-lookup"><span data-stu-id="f3f6d-119">2.1</span></span>

  <span data-ttu-id="f3f6d-120">Es posible que el SDK o el entorno de ejecución que intenta descargar no esté disponible para su distribución de Linux.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-120">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="f3f6d-121">Para obtener una lista de las distribuciones admitidas, consulte [Dependencias y requisitos de .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="f3f6d-121">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="f3f6d-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f3f6d-122">Examples</span></span>

- <span data-ttu-id="f3f6d-123">Instalación del entorno de ejecución de ASP.NET Core 5.0: `aspnetcore-runtime-5.0`</span><span class="sxs-lookup"><span data-stu-id="f3f6d-123">Install the ASP.NET Core 5.0 runtime: `aspnetcore-runtime-5.0`</span></span>
- <span data-ttu-id="f3f6d-124">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="f3f6d-124">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="f3f6d-125">Instalación del SDK de .NET 5.0: `dotnet-sdk-5.0`</span><span class="sxs-lookup"><span data-stu-id="f3f6d-125">Install the .NET 5.0 SDK: `dotnet-sdk-5.0`</span></span>
- <span data-ttu-id="f3f6d-126">Instalación del SDK de .NET Core 3.1: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="f3f6d-126">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="f3f6d-127">Falta el paquete</span><span class="sxs-lookup"><span data-stu-id="f3f6d-127">Package missing</span></span>

<span data-ttu-id="f3f6d-128">Si la combinación de paquete y versión no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-128">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="f3f6d-129">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-129">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET SDK.</span></span> <span data-ttu-id="f3f6d-130">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="f3f6d-130">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="f3f6d-131">Para obtener una lista de las distribuciones de Linux compatibles con .NET, vea [Dependencias y requisitos de .NET](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="f3f6d-131">For a list of Linux distributions supported by .NET Core, see [.NET dependencies and requirements](../linux.md).</span></span>
