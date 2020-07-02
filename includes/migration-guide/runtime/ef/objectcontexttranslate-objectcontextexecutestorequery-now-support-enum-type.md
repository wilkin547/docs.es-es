---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620629"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="0ea69-101">Los métodos ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admiten el tipo enum</span><span class="sxs-lookup"><span data-stu-id="0ea69-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="0ea69-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ea69-102">Details</span></span>

<span data-ttu-id="0ea69-103">En .NET Framework 4.0, el parámetro genérico <code>T</code> de los métodos <code>ObjectContext.Translate</code> y <code>ObjectContext.ExecuteStoreQuery</code> no podía ser una enumeración.</span><span class="sxs-lookup"><span data-stu-id="0ea69-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="0ea69-104">Ahora se admite este escenario.</span><span class="sxs-lookup"><span data-stu-id="0ea69-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0ea69-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0ea69-105">Suggestion</span></span>

<span data-ttu-id="0ea69-106">Si se llamaba a Translate o ExecuteStoreQuery en un tipo de enumeración en .NET Framework 4.0, se devolvía "0".</span><span class="sxs-lookup"><span data-stu-id="0ea69-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="0ea69-107">Si este era el comportamiento deseado, las llamadas deberían reemplazarse por una constante 0 (o su tipo enum equivalente).</span><span class="sxs-lookup"><span data-stu-id="0ea69-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="0ea69-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0ea69-108">Name</span></span>    | <span data-ttu-id="0ea69-109">Valor</span><span class="sxs-lookup"><span data-stu-id="0ea69-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0ea69-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0ea69-110">Scope</span></span>   |<span data-ttu-id="0ea69-111">Borde</span><span class="sxs-lookup"><span data-stu-id="0ea69-111">Edge</span></span>|
|<span data-ttu-id="0ea69-112">Versión</span><span class="sxs-lookup"><span data-stu-id="0ea69-112">Version</span></span>|<span data-ttu-id="0ea69-113">4.5</span><span class="sxs-lookup"><span data-stu-id="0ea69-113">4.5</span></span>|
|<span data-ttu-id="0ea69-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ea69-114">Type</span></span>|<span data-ttu-id="0ea69-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0ea69-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0ea69-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0ea69-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
