---
title: '* (Multiplicar) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: cddcaa61c6241b5f5a37bac96ef08c3322367823
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146424"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="70796-102">\* (Multiplicar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="70796-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="70796-103">Multiplica dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="70796-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70796-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70796-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="70796-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="70796-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="70796-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="70796-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="70796-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="70796-107">Result Types</span></span>  
 <span data-ttu-id="70796-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="70796-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="70796-109">Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="70796-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70796-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70796-110">Example</span></span>  
 <span data-ttu-id="70796-111">La siguiente consulta de Entity SQL usa el operador aritmético \* para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="70796-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="70796-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="70796-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="70796-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="70796-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="70796-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="70796-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="70796-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="70796-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="70796-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="70796-116">See also</span></span>

- [<span data-ttu-id="70796-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="70796-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
