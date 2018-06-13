---
title: '- (Negativo) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 5d1726be6a4a59891646d05b344f59962d548c75
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765157"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="04191-102">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="04191-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="04191-103">Devuelve el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="04191-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04191-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04191-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="04191-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="04191-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="04191-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="04191-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="04191-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="04191-107">Result Types</span></span>  
 <span data-ttu-id="04191-108">Tipo de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="04191-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04191-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04191-109">Remarks</span></span>  
 <span data-ttu-id="04191-110">Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="04191-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="04191-111">Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="04191-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04191-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04191-112">Example</span></span>  
 <span data-ttu-id="04191-113">La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="04191-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="04191-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="04191-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="04191-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="04191-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="04191-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="04191-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="04191-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="04191-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="04191-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="04191-118">See Also</span></span>  
 [<span data-ttu-id="04191-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="04191-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
