---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901786"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="c0850-101">Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c0850-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="c0850-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depende de las [bibliotecas de Azure Storage](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="c0850-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="c0850-103">Estas bibliotecas han cambiado el nombre de los ensamblados, paquetes y espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c0850-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="c0850-104">A partir de ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` utiliza las nuevas API y paquetes con prefijo `Microsoft.Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="c0850-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="c0850-105">Si tiene preguntas sobre las API de Azure Storage, utilice <https://github.com/Azure/azure-storage-net>.</span><span class="sxs-lookup"><span data-stu-id="c0850-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="c0850-106">Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="c0850-106">For discussion on this issue, see [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c0850-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c0850-107">Version introduced</span></span>

<span data-ttu-id="c0850-108">3.0</span><span class="sxs-lookup"><span data-stu-id="c0850-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c0850-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c0850-109">Old behavior</span></span>

<span data-ttu-id="c0850-110">El paquete hacía referencia al paquete NuGet `WindowsAzure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="c0850-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c0850-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c0850-111">New behavior</span></span>

<span data-ttu-id="c0850-112">El paquete hace referencia al paquete NuGet `Microsoft.Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="c0850-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c0850-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c0850-113">Reason for change</span></span>

<span data-ttu-id="c0850-114">Este cambio permite a `Microsoft.AspNetCore.DataProtection.AzureStorage` migrar a los paquetes de Azure Storage recomendados.</span><span class="sxs-lookup"><span data-stu-id="c0850-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c0850-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c0850-115">Recommended action</span></span>

<span data-ttu-id="c0850-116">Si todavía necesita usar las API de Azure Storage anteriores con ASP.NET Core 3.0, agregue una dependencia directa al paquete [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/).</span><span class="sxs-lookup"><span data-stu-id="c0850-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="c0850-117">Este paquete se puede instalar junto con las nuevas API de `Microsoft.Azure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="c0850-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="c0850-118">En muchos casos, la actualización solo implica cambiar las instrucciones `using` para usar los espacios de nombres nuevos:</span><span class="sxs-lookup"><span data-stu-id="c0850-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="c0850-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="c0850-119">Category</span></span>

<span data-ttu-id="c0850-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0850-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0850-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c0850-121">Affected APIs</span></span>

<span data-ttu-id="c0850-122">None</span><span class="sxs-lookup"><span data-stu-id="c0850-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
