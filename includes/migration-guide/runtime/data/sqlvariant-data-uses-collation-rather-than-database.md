---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235837"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="09270-101">Los datos de sql_variant usan la intercalación de sql_variant en lugar de la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="09270-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="09270-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="09270-102">Details</span></span>|<span data-ttu-id="09270-103">Los datos de <code>sql_variant</code> utilizan la intercalación de <code>sql_variant</code> en lugar de la intercalación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="09270-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="09270-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="09270-104">Suggestion</span></span>|<span data-ttu-id="09270-105">Este cambio soluciona posibles daños en los datos si la intercalación de la base de datos difiere de la intercalación de <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="09270-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="09270-106">Las aplicaciones que se basan en datos dañados pueden experimentar errores.</span><span class="sxs-lookup"><span data-stu-id="09270-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="09270-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="09270-107">Scope</span></span>|<span data-ttu-id="09270-108">Transparente</span><span class="sxs-lookup"><span data-stu-id="09270-108">Transparent</span></span>|
|<span data-ttu-id="09270-109">Versión</span><span class="sxs-lookup"><span data-stu-id="09270-109">Version</span></span>|<span data-ttu-id="09270-110">4.5</span><span class="sxs-lookup"><span data-stu-id="09270-110">4.5</span></span>|
|<span data-ttu-id="09270-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="09270-111">Type</span></span>|<span data-ttu-id="09270-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09270-112">Runtime</span></span>|
