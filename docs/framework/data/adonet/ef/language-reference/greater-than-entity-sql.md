---
title: '&gt; (Mayor que) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 1449af09022a9e11be1f3627023318270adf0121
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736934"
---
# <a name="gt-greater-than-entity-sql"></a><span data-ttu-id="acf10-102">&gt; (Mayor que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="acf10-102">&gt; (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="acf10-103">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="acf10-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf10-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acf10-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="acf10-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="acf10-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="acf10-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="acf10-106">Any valid expression.</span></span> <span data-ttu-id="acf10-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="acf10-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="acf10-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="acf10-108">Result Types</span></span>  
 <span data-ttu-id="acf10-109">`true` si la expresión izquierda tiene un valor mayor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="acf10-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acf10-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acf10-110">Example</span></span>  
 <span data-ttu-id="acf10-111">La consulta de Entity SQL siguiente utiliza el operador de comparación > para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor mayor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="acf10-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="acf10-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="acf10-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="acf10-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="acf10-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="acf10-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="acf10-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="acf10-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="acf10-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="acf10-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="acf10-116">See also</span></span>
- [<span data-ttu-id="acf10-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="acf10-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
