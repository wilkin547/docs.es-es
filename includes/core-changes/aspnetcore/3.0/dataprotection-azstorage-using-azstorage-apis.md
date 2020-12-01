---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032738"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a><span data-ttu-id="61b95-101">Protección de datos: uso de nuevas API de Azure Storage por parte de DataProtection.Blobs</span><span class="sxs-lookup"><span data-stu-id="61b95-101">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>

<span data-ttu-id="61b95-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` depende de las [bibliotecas de Azure Storage](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="61b95-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="61b95-103">Estas bibliotecas han cambiado el nombre de los ensamblados, paquetes y espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="61b95-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="61b95-104">A partir de ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` utiliza las nuevas API y paquetes con prefijo `Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="61b95-104">Starting in ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` uses the new `Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="61b95-105">Si tiene preguntas sobre las API de Azure Storage, utilice <https://github.com/Azure/azure-storage-net>.</span><span class="sxs-lookup"><span data-stu-id="61b95-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="61b95-106">Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="61b95-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="61b95-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="61b95-107">Version introduced</span></span>

<span data-ttu-id="61b95-108">3.0</span><span class="sxs-lookup"><span data-stu-id="61b95-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="61b95-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="61b95-109">Old behavior</span></span>

<span data-ttu-id="61b95-110">El paquete hacía referencia al paquete NuGet `WindowsAzure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="61b95-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>
<span data-ttu-id="61b95-111">El paquete hace referencia al paquete NuGet `Microsoft.Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="61b95-111">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="61b95-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="61b95-112">New behavior</span></span>

<span data-ttu-id="61b95-113">El paquete hace referencia al paquete NuGet `Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="61b95-113">The package references the `Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="61b95-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="61b95-114">Reason for change</span></span>

<span data-ttu-id="61b95-115">Este cambio permite a `Azure.Extensions.AspNetCore.DataProtection.Blobs` migrar a los paquetes de Azure Storage recomendados.</span><span class="sxs-lookup"><span data-stu-id="61b95-115">This change allows `Azure.Extensions.AspNetCore.DataProtection.Blobs` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="61b95-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="61b95-116">Recommended action</span></span>

<span data-ttu-id="61b95-117">Si todavía necesita usar las API de Azure Storage anteriores con ASP.NET Core 3.0, agregue una dependencia directa al paquete [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) o [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span><span class="sxs-lookup"><span data-stu-id="61b95-117">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the package [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) or [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span></span> <span data-ttu-id="61b95-118">Este paquete se puede instalar junto con las nuevas API de `Azure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="61b95-118">This package can be installed alongside the new `Azure.Storage` APIs.</span></span>

<span data-ttu-id="61b95-119">En muchos casos, la actualización solo implica cambiar las instrucciones `using` para usar los espacios de nombres nuevos:</span><span class="sxs-lookup"><span data-stu-id="61b95-119">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a><span data-ttu-id="61b95-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="61b95-120">Category</span></span>

<span data-ttu-id="61b95-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="61b95-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="61b95-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="61b95-122">Affected APIs</span></span>

<span data-ttu-id="61b95-123">None</span><span class="sxs-lookup"><span data-stu-id="61b95-123">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
