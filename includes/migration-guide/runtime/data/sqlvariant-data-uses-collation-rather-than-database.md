---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497203"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="41f3f-101">Los datos de sql_variant usan la intercalación de sql_variant en lugar de la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="41f3f-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="41f3f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="41f3f-102">Details</span></span>

<span data-ttu-id="41f3f-103">Los datos de <code>sql_variant</code> utilizan la intercalación de <code>sql_variant</code> en lugar de la intercalación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="41f3f-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="41f3f-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="41f3f-104">Suggestion</span></span>

<span data-ttu-id="41f3f-105">Este cambio soluciona posibles daños en los datos si la intercalación de la base de datos difiere de la intercalación de <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="41f3f-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="41f3f-106">Las aplicaciones que se basan en datos dañados pueden experimentar errores.</span><span class="sxs-lookup"><span data-stu-id="41f3f-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="41f3f-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="41f3f-107">Name</span></span>    | <span data-ttu-id="41f3f-108">Valor</span><span class="sxs-lookup"><span data-stu-id="41f3f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="41f3f-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="41f3f-109">Scope</span></span>   |<span data-ttu-id="41f3f-110">Transparente</span><span class="sxs-lookup"><span data-stu-id="41f3f-110">Transparent</span></span>|
|<span data-ttu-id="41f3f-111">Versión</span><span class="sxs-lookup"><span data-stu-id="41f3f-111">Version</span></span>|<span data-ttu-id="41f3f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="41f3f-112">4.5</span></span>|
|<span data-ttu-id="41f3f-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="41f3f-113">Type</span></span>|<span data-ttu-id="41f3f-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="41f3f-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="41f3f-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="41f3f-115">Affected APIs</span></span>

<span data-ttu-id="41f3f-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="41f3f-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
