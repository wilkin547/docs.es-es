---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319184"
---
# <a name="where-entity-sql"></a><span data-ttu-id="0fdef-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0fdef-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="0fdef-103">La cláusula WHERE se aplica directamente después de la cláusula [from](from-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="0fdef-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fdef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fdef-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fdef-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0fdef-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0fdef-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="0fdef-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fdef-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fdef-107">Remarks</span></span>  
 <span data-ttu-id="0fdef-108">La cláusula WHERE tiene la misma semántica que se describe en Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0fdef-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="0fdef-109">Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.</span><span class="sxs-lookup"><span data-stu-id="0fdef-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="0fdef-110">La expresión `e` debe tener el tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="0fdef-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="0fdef-111">La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección.</span><span class="sxs-lookup"><span data-stu-id="0fdef-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="0fdef-112">Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="0fdef-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fdef-113">See also</span></span>

- [<span data-ttu-id="0fdef-114">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0fdef-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="0fdef-115">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="0fdef-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
