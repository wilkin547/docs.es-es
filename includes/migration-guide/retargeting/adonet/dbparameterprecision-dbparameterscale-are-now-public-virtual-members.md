---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616111"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="0de73-101">DbParameter.Precision y DbParameter.Scale son ahora miembros virtuales públicos</span><span class="sxs-lookup"><span data-stu-id="0de73-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="0de73-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0de73-102">Details</span></span>

<span data-ttu-id="0de73-103"><xref:System.Data.Common.DbParameter.Precision> y <xref:System.Data.Common.DbParameter.Scale> se implementan como propiedades públicas virtuales.</span><span class="sxs-lookup"><span data-stu-id="0de73-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="0de73-104">Reemplazan las implementaciones de interfaz explícitas correspondientes, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> y <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="0de73-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0de73-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0de73-105">Suggestion</span></span>

<span data-ttu-id="0de73-106">Al volver a compilar un proveedor de base de datos de ADO.NET, estas diferencias necesitarán que se aplique la palabra clave "override" a las propiedades Scale y Precision.</span><span class="sxs-lookup"><span data-stu-id="0de73-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="0de73-107">Esto solo es necesario al volver a compilar los componentes; los archivos binarios existentes continuarán funcionando.</span><span class="sxs-lookup"><span data-stu-id="0de73-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="0de73-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0de73-108">Name</span></span>    | <span data-ttu-id="0de73-109">Valor</span><span class="sxs-lookup"><span data-stu-id="0de73-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0de73-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0de73-110">Scope</span></span>   | <span data-ttu-id="0de73-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="0de73-111">Minor</span></span>       |
| <span data-ttu-id="0de73-112">Versión</span><span class="sxs-lookup"><span data-stu-id="0de73-112">Version</span></span> | <span data-ttu-id="0de73-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0de73-113">4.5.1</span></span>       |
| <span data-ttu-id="0de73-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="0de73-114">Type</span></span>    | <span data-ttu-id="0de73-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="0de73-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0de73-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0de73-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
