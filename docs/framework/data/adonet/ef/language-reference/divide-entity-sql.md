---
title: '- (Dividir) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 42fc5e2a9f9f159a8a60973dbed6540b3188fba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745241"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="1357c-102">/ (Dividir) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1357c-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="1357c-103">Divide un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="1357c-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1357c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1357c-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="1357c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1357c-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="1357c-106">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="1357c-106">The numeric expression to divide.</span></span> <span data-ttu-id="1357c-107">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="1357c-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="1357c-108">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="1357c-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="1357c-109">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="1357c-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1357c-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1357c-110">Result Types</span></span>  
 <span data-ttu-id="1357c-111">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="1357c-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="1357c-112">Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1357c-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1357c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1357c-113">Example</span></span>  
 <span data-ttu-id="1357c-114">La siguiente consulta de Entity SQL usa el aritmético / operador para dividir un número por otro.</span><span class="sxs-lookup"><span data-stu-id="1357c-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="1357c-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1357c-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1357c-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1357c-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1357c-117">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1357c-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1357c-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1357c-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="1357c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1357c-119">See also</span></span>
- [<span data-ttu-id="1357c-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1357c-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
