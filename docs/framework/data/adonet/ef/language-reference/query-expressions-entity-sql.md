---
title: Expresiones de consulta (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: ca6b79b4b3d3326a74780345decf58367596adb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175608"
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="5f481-102">Expresiones de consulta (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f481-102">Query Expressions (Entity SQL)</span></span>

<span data-ttu-id="5f481-103">Una expresión de consulta combina muchos operadores de consulta diferentes en una sintaxis única.</span><span class="sxs-lookup"><span data-stu-id="5f481-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5f481-104">proporciona varios tipos de expresiones, entre las que se incluyen los [literales](literals-entity-sql.md), [parámetros](parameters-entity-sql.md), [variables](variables-entity-sql.md), operadores, [funciones](functions-entity-sql.md), operadores de conjuntos, etc.</span><span class="sxs-lookup"><span data-stu-id="5f481-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="5f481-105">Para obtener más información, vea [referencia de Entity SQL](entity-sql-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5f481-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="5f481-106">Cláusulas</span><span class="sxs-lookup"><span data-stu-id="5f481-106">Clauses</span></span>  

 <span data-ttu-id="5f481-107">Una expresión de consulta se compone de una serie de cláusulas que aplican operaciones sucesivas a una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="5f481-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="5f481-108">Se basan en las mismas cláusulas que se encuentran en una instrucción SELECT de SQL estándar: [Select](select-entity-sql.md), [from](from-entity-sql.md), [Where](where-entity-sql.md), [Group by](group-by-entity-sql.md), [having](having-entity-sql.md)y [order by](order-by-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5f481-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="5f481-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5f481-109">Scope</span></span>  

 <span data-ttu-id="5f481-110">Los nombres que se definen en la cláusula FROM se incluyen en el ámbito de FROM en orden de aparición, de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5f481-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="5f481-111">En la lista de JOIN, las expresiones pueden hacer referencia a los nombres que se definieron en la lista anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5f481-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="5f481-112">Las propiedades públicas de los elementos identificados en la cláusula FROM no se agregan al ámbito de FROM. Siempre se debe hacer referencia a ellas mediante el nombre completo del alias.</span><span class="sxs-lookup"><span data-stu-id="5f481-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="5f481-113">Normalmente, todas las partes de la expresión SELECT se consideran dentro del ámbito de FROM.</span><span class="sxs-lookup"><span data-stu-id="5f481-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f481-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f481-114">See also</span></span>

- [<span data-ttu-id="5f481-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5f481-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
