---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920665"
---

<span data-ttu-id="17ba5-101">Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="17ba5-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="17ba5-102">**product**</span><span class="sxs-lookup"><span data-stu-id="17ba5-102">**product**</span></span>\
<span data-ttu-id="17ba5-103">Tipo de producto .NET que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="17ba5-103">The type of .NET product to install.</span></span> <span data-ttu-id="17ba5-104">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="17ba5-104">Valid options are:</span></span>

  - <span data-ttu-id="17ba5-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="17ba5-105">dotnet</span></span>
  - <span data-ttu-id="17ba5-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="17ba5-106">aspnetcore</span></span>

- <span data-ttu-id="17ba5-107">**type**</span><span class="sxs-lookup"><span data-stu-id="17ba5-107">**type**</span></span>\
<span data-ttu-id="17ba5-108">Elige el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="17ba5-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="17ba5-109">Las opciones válidas son:</span><span class="sxs-lookup"><span data-stu-id="17ba5-109">Valid options are:</span></span>

  - <span data-ttu-id="17ba5-110">sdk</span><span class="sxs-lookup"><span data-stu-id="17ba5-110">sdk</span></span>
  - <span data-ttu-id="17ba5-111">motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="17ba5-111">runtime</span></span>

- <span data-ttu-id="17ba5-112">**version**</span><span class="sxs-lookup"><span data-stu-id="17ba5-112">**version**</span></span>\
<span data-ttu-id="17ba5-113">Versión del SDK o del entorno de ejecución que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="17ba5-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="17ba5-114">En este artículo se proporcionarán siempre las instrucciones para la última versión admitida.</span><span class="sxs-lookup"><span data-stu-id="17ba5-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="17ba5-115">Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="17ba5-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="17ba5-116">3.0</span><span class="sxs-lookup"><span data-stu-id="17ba5-116">3.0</span></span>
  - <span data-ttu-id="17ba5-117">2.2</span><span class="sxs-lookup"><span data-stu-id="17ba5-117">2.2</span></span>
  - <span data-ttu-id="17ba5-118">2.1</span><span class="sxs-lookup"><span data-stu-id="17ba5-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="17ba5-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17ba5-119">Examples</span></span>

- <span data-ttu-id="17ba5-120">Instalación del SDK de .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="17ba5-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="17ba5-121">Instalación del runtime de ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="17ba5-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="17ba5-122">Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="17ba5-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="17ba5-123">Falta el paquete</span><span class="sxs-lookup"><span data-stu-id="17ba5-123">Package missing</span></span>

<span data-ttu-id="17ba5-124">Si la combinación de paquete y versión no funciona, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="17ba5-124">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="17ba5-125">Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="17ba5-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="17ba5-126">El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="17ba5-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span>
