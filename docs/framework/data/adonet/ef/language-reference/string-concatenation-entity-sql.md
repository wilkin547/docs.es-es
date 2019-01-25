---
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: e53bd0a2607deb67d45edc44e51cf4ad283b21c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54633938"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="3148a-102">+ (Concatenación de cadenas) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3148a-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="3148a-103">Concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="3148a-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3148a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3148a-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3148a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3148a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3148a-106">Cualquier expresión válida de los tipos de datos EDM.String.</span><span class="sxs-lookup"><span data-stu-id="3148a-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="3148a-107">Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.</span><span class="sxs-lookup"><span data-stu-id="3148a-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3148a-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="3148a-108">Result Types</span></span>  
 <span data-ttu-id="3148a-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="3148a-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="3148a-110">Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3148a-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3148a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3148a-111">Example</span></span>  
 <span data-ttu-id="3148a-112">La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="3148a-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="3148a-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3148a-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3148a-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3148a-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3148a-115">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3148a-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="3148a-116">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3148a-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="3148a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3148a-117">See also</span></span>
- [<span data-ttu-id="3148a-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3148a-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="3148a-119">Tipos de modelos conceptuales (CSDL)</span><span class="sxs-lookup"><span data-stu-id="3148a-119">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
