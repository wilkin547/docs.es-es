---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198572"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="842ea-101">Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient</span><span class="sxs-lookup"><span data-stu-id="842ea-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="842ea-102">El paquete `Microsoft.Extensions.Caching.SqlServer` usará el paquete nuevo `Microsoft.Data.SqlClient` en lugar del `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="842ea-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="842ea-103">Este cambio podría producir pequeños cambios en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="842ea-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="842ea-104">Para obtener más información, vea [Introducción al nuevo Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span><span class="sxs-lookup"><span data-stu-id="842ea-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="842ea-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="842ea-105">Version introduced</span></span>

<span data-ttu-id="842ea-106">3.0</span><span class="sxs-lookup"><span data-stu-id="842ea-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="842ea-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="842ea-107">Old behavior</span></span>

<span data-ttu-id="842ea-108">El paquete `Microsoft.Extensions.Caching.SqlServer` usaba el paquete `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="842ea-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="842ea-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="842ea-109">New behavior</span></span>

<span data-ttu-id="842ea-110">`Microsoft.Extensions.Caching.SqlServer` ahora usa el paquete `Microsoft.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="842ea-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="842ea-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="842ea-111">Reason for change</span></span>

<span data-ttu-id="842ea-112">`Microsoft.Data.SqlClient` es un nuevo paquete que se ha creado a partir de `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="842ea-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="842ea-113">A partir de ahora, aquí es donde se realizará todo el trabajo de las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="842ea-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="842ea-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="842ea-114">Recommended action</span></span>

<span data-ttu-id="842ea-115">Los clientes no deben preocuparse por este cambio importante, a menos que usaran los tipos que devolvía el paquete `Microsoft.Extensions.Caching.SqlServer` y los convirtieran en tipos de `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="842ea-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="842ea-116">Por ejemplo, si algún usuario estuviera convirtiendo un elemento `DbConnection` al [tipo de SqlConnection anterior](xref:System.Data.SqlClient.SqlConnection), tendría que cambiar la conversión al nuevo tipo de `Microsoft.Data.SqlClient.SqlConnection`.</span><span class="sxs-lookup"><span data-stu-id="842ea-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="842ea-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="842ea-117">Category</span></span>

<span data-ttu-id="842ea-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="842ea-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="842ea-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="842ea-119">Affected APIs</span></span>

<span data-ttu-id="842ea-120">None</span><span class="sxs-lookup"><span data-stu-id="842ea-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
