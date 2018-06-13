---
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 1826d1267f0ee5ad8320cf1d1ab36f87adf765a5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764559"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="40c92-102">+ (Concatenación de cadenas) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="40c92-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="40c92-103">Concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="40c92-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40c92-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="40c92-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="40c92-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="40c92-106">Cualquier expresión válida de los tipos de datos EDM.String.</span><span class="sxs-lookup"><span data-stu-id="40c92-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="40c92-107">Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.</span><span class="sxs-lookup"><span data-stu-id="40c92-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="40c92-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="40c92-108">Result Types</span></span>  
 <span data-ttu-id="40c92-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="40c92-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="40c92-110">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="40c92-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40c92-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40c92-111">Example</span></span>  
 <span data-ttu-id="40c92-112">La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="40c92-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="40c92-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="40c92-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="40c92-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="40c92-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="40c92-115">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="40c92-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="40c92-116">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="40c92-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="40c92-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c92-117">See Also</span></span>  
 [<span data-ttu-id="40c92-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="40c92-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="40c92-119">Tipos de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="40c92-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
