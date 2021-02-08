---
description: 'Más información acerca de: = (es igual a) (Entity SQL)'
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 500c3fdde2377b3b5160436f23d051c2bcd0ee62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786412"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="215fb-103">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="215fb-103">= (Equals) (Entity SQL)</span></span>

<span data-ttu-id="215fb-104">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="215fb-104">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="215fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="215fb-105">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="215fb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="215fb-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="215fb-107">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="215fb-107">Any valid expression.</span></span> <span data-ttu-id="215fb-108">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="215fb-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="215fb-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="215fb-109">Result Types</span></span>  

 <span data-ttu-id="215fb-110">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="215fb-110">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="215fb-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="215fb-111">Remarks</span></span>  

 <span data-ttu-id="215fb-112">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="215fb-112">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="215fb-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="215fb-113">Example</span></span>  

 <span data-ttu-id="215fb-114">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="215fb-114">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="215fb-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="215fb-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="215fb-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="215fb-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="215fb-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="215fb-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="215fb-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="215fb-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="215fb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="215fb-119">See also</span></span>

- [<span data-ttu-id="215fb-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="215fb-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
