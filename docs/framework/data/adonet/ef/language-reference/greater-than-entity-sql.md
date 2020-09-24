---
title: '>  (Mayor que) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 52a9f9f645aa51402ceb8cb0a40d2040d1c0802c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147949"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="ceb66-102">> (mayor que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ceb66-102">> (Greater Than) (Entity SQL)</span></span>

<span data-ttu-id="ceb66-103">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="ceb66-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ceb66-104">Syntax</span></span>  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ceb66-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ceb66-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="ceb66-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="ceb66-106">Any valid expression.</span></span> <span data-ttu-id="ceb66-107">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="ceb66-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ceb66-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ceb66-108">Result Types</span></span>  

 <span data-ttu-id="ceb66-109">`true` si la expresión izquierda tiene un valor mayor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ceb66-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb66-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ceb66-110">Example</span></span>  

 <span data-ttu-id="ceb66-111">La consulta de Entity SQL siguiente utiliza el operador de comparación > para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor mayor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="ceb66-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="ceb66-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ceb66-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ceb66-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ceb66-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ceb66-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ceb66-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ceb66-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ceb66-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="ceb66-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceb66-116">See also</span></span>

- [<span data-ttu-id="ceb66-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ceb66-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
