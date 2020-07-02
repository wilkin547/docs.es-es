---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620614"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="210dd-101">Control de excepciones diferente para los métodos ObjectContext.CreateDatabase y DbProviderServices.CreateDatabase</span><span class="sxs-lookup"><span data-stu-id="210dd-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="210dd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="210dd-102">Details</span></span>

<span data-ttu-id="210dd-103">A partir de .NET Framework 4.5, si se produce un error en la creación de la base de datos, los métodos <code>CreateDatabase</code> intentarán eliminar la base de datos vacía.</span><span class="sxs-lookup"><span data-stu-id="210dd-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="210dd-104">Si esa operación se realiza correctamente, se propagará la excepción <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> original (en lugar de la excepción <xref:System.InvalidOperationException?displayProperty=fullName>, que siempre se iniciaba en .NET Framework 4.0).</span><span class="sxs-lookup"><span data-stu-id="210dd-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="210dd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="210dd-105">Suggestion</span></span>

<span data-ttu-id="210dd-106">Cuando se detecta una excepción <xref:System.InvalidOperationException?displayProperty=fullName> al ejecutar <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ahora también se deben detectar las excepciones SQLExceptions.</span><span class="sxs-lookup"><span data-stu-id="210dd-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="210dd-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="210dd-107">Name</span></span>    | <span data-ttu-id="210dd-108">Valor</span><span class="sxs-lookup"><span data-stu-id="210dd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="210dd-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="210dd-109">Scope</span></span>   |<span data-ttu-id="210dd-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="210dd-110">Minor</span></span>|
|<span data-ttu-id="210dd-111">Versión</span><span class="sxs-lookup"><span data-stu-id="210dd-111">Version</span></span>|<span data-ttu-id="210dd-112">4.5</span><span class="sxs-lookup"><span data-stu-id="210dd-112">4.5</span></span>|
|<span data-ttu-id="210dd-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="210dd-113">Type</span></span>|<span data-ttu-id="210dd-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="210dd-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="210dd-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="210dd-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
