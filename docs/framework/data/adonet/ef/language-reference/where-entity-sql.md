---
description: 'Más información acerca de: Dónde (Entity SQL)'
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: e094a93927f6ac77aef772654f1d8d4fcf999cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712875"
---
# <a name="where-entity-sql"></a><span data-ttu-id="f6b0d-103">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f6b0d-103">WHERE (Entity SQL)</span></span>

<span data-ttu-id="f6b0d-104">La cláusula WHERE se aplica directamente después de la cláusula [from](from-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="f6b0d-104">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b0d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6b0d-105">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6b0d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f6b0d-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="f6b0d-107">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-107">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b0d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f6b0d-108">Remarks</span></span>  

 <span data-ttu-id="f6b0d-109">La cláusula WHERE tiene la misma semántica que se describe en Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-109">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="f6b0d-110">Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-110">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="f6b0d-111">La expresión `e` debe tener el tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-111">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="f6b0d-112">La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-112">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="f6b0d-113">Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f6b0d-113">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b0d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6b0d-114">See also</span></span>

- [<span data-ttu-id="f6b0d-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f6b0d-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f6b0d-116">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="f6b0d-116">Query Expressions</span></span>](query-expressions-entity-sql.md)
