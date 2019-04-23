---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230712"
---
# <a name="where-entity-sql"></a><span data-ttu-id="6b962-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6b962-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="6b962-103">La cláusula WHERE se aplica directamente después del [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="6b962-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b962-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b962-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b962-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b962-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6b962-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="6b962-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b962-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b962-107">Remarks</span></span>  
 <span data-ttu-id="6b962-108">La cláusula WHERE tiene la misma semántica que la descrita para [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b962-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6b962-109">Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.</span><span class="sxs-lookup"><span data-stu-id="6b962-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="6b962-110">La expresión `e` debe tener el tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="6b962-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="6b962-111">La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección.</span><span class="sxs-lookup"><span data-stu-id="6b962-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="6b962-112">Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="6b962-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b962-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b962-113">See also</span></span>

- [<span data-ttu-id="6b962-114">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6b962-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6b962-115">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="6b962-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
