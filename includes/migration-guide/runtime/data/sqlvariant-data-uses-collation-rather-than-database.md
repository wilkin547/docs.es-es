---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620605"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="faa9e-101">Los datos de sql_variant usan la intercalación de sql_variant en lugar de la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="faa9e-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="faa9e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="faa9e-102">Details</span></span>

<span data-ttu-id="faa9e-103">Los datos de <code>sql_variant</code> utilizan la intercalación de <code>sql_variant</code> en lugar de la intercalación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="faa9e-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="faa9e-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="faa9e-104">Suggestion</span></span>

<span data-ttu-id="faa9e-105">Este cambio soluciona posibles daños en los datos si la intercalación de la base de datos difiere de la intercalación de <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="faa9e-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="faa9e-106">Las aplicaciones que se basan en datos dañados pueden experimentar errores.</span><span class="sxs-lookup"><span data-stu-id="faa9e-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="faa9e-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="faa9e-107">Name</span></span>    | <span data-ttu-id="faa9e-108">Valor</span><span class="sxs-lookup"><span data-stu-id="faa9e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="faa9e-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="faa9e-109">Scope</span></span>   |<span data-ttu-id="faa9e-110">Transparente</span><span class="sxs-lookup"><span data-stu-id="faa9e-110">Transparent</span></span>|
|<span data-ttu-id="faa9e-111">Versión</span><span class="sxs-lookup"><span data-stu-id="faa9e-111">Version</span></span>|<span data-ttu-id="faa9e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="faa9e-112">4.5</span></span>|
|<span data-ttu-id="faa9e-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="faa9e-113">Type</span></span>|<span data-ttu-id="faa9e-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="faa9e-114">Runtime</span></span>|
