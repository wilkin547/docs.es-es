---
title: '* Multiplica (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 7006f5143e8cc18156f748ae7664f3787c9ff5c9
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319612"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="3e363-102">\* (Multiplicar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3e363-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="3e363-103">Multiplica dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="3e363-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e363-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e363-104">Syntax</span></span>  
  
```sql  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e363-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3e363-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3e363-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="3e363-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3e363-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="3e363-107">Result Types</span></span>  
 <span data-ttu-id="3e363-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="3e363-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="3e363-109">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3e363-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e363-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e363-110">Example</span></span>  
 <span data-ttu-id="3e363-111">La siguiente consulta de Entity SQL usa el operador aritmético \* para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="3e363-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="3e363-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3e363-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3e363-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3e363-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3e363-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3e363-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3e363-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3e363-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTIPLY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="3e363-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e363-116">See also</span></span>

- [<span data-ttu-id="3e363-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3e363-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
