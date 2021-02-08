---
description: 'Más información sobre: + (concatenación de cadenas) (Entity SQL)'
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 7b6aac5b865e2127bb23446248e20d83ea3c7ea3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791847"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="89f6b-103">+ (Concatenación de cadenas) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="89f6b-103">+ (String Concatenation) (Entity SQL)</span></span>

<span data-ttu-id="89f6b-104">Concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="89f6b-104">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f6b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89f6b-105">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="89f6b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89f6b-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="89f6b-107">Cualquier expresión válida de los tipos de datos EDM.String.</span><span class="sxs-lookup"><span data-stu-id="89f6b-107">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="89f6b-108">Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.</span><span class="sxs-lookup"><span data-stu-id="89f6b-108">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="89f6b-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="89f6b-109">Result Types</span></span>  

 <span data-ttu-id="89f6b-110">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="89f6b-110">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="89f6b-111">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="89f6b-111">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89f6b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89f6b-112">Example</span></span>  

 <span data-ttu-id="89f6b-113">La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="89f6b-113">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="89f6b-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="89f6b-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="89f6b-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="89f6b-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="89f6b-116">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="89f6b-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="89f6b-117">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="89f6b-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="89f6b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="89f6b-118">See also</span></span>

- [<span data-ttu-id="89f6b-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="89f6b-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="89f6b-120">Tipos de modelos conceptuales (CSDL)</span><span class="sxs-lookup"><span data-stu-id="89f6b-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
