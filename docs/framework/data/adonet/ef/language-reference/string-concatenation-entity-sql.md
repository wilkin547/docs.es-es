---
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319311"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="bd8b2-102">+ (Concatenación de cadenas) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bd8b2-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="bd8b2-103">Concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd8b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd8b2-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bd8b2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bd8b2-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bd8b2-106">Cualquier expresión válida de los tipos de datos EDM.String.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="bd8b2-107">Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bd8b2-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="bd8b2-108">Result Types</span></span>  
 <span data-ttu-id="bd8b2-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="bd8b2-110">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bd8b2-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd8b2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd8b2-111">Example</span></span>  
 <span data-ttu-id="bd8b2-112">La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="bd8b2-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8b2-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bd8b2-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bd8b2-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bd8b2-115">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bd8b2-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="bd8b2-116">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bd8b2-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="bd8b2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd8b2-117">See also</span></span>

- [<span data-ttu-id="bd8b2-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bd8b2-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="bd8b2-119">Tipos de modelos conceptuales (CSDL)</span><span class="sxs-lookup"><span data-stu-id="bd8b2-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
