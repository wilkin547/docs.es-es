---
description: 'Más información acerca de: * (multiplicar) (Entity SQL)'
title: '* Multiplica (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 92606e5f9e4646ab651d0e07095e6f419401188f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696625"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="06695-103">\* (Multiplicar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="06695-103">\* (Multiply) (Entity SQL)</span></span>

<span data-ttu-id="06695-104">Multiplica dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="06695-104">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06695-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06695-105">Syntax</span></span>  
  
```sql  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="06695-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="06695-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="06695-107">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="06695-107">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="06695-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="06695-108">Result Types</span></span>  

 <span data-ttu-id="06695-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="06695-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="06695-110">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="06695-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06695-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06695-111">Example</span></span>  

 <span data-ttu-id="06695-112">La siguiente consulta de Entity SQL usa el operador aritmético \* para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="06695-112">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="06695-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="06695-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="06695-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="06695-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="06695-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="06695-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="06695-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="06695-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTIPLY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="06695-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="06695-117">See also</span></span>

- [<span data-ttu-id="06695-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="06695-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
