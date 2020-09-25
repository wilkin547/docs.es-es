---
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204416"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="86998-102">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="86998-102">- (Negative) (Entity SQL)</span></span>

<span data-ttu-id="86998-103">Devuelve el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="86998-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86998-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86998-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="86998-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="86998-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="86998-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="86998-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="86998-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="86998-107">Result Types</span></span>  

 <span data-ttu-id="86998-108">El tipo de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="86998-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86998-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86998-109">Remarks</span></span>  

 <span data-ttu-id="86998-110">Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="86998-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="86998-111">Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="86998-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86998-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86998-112">Example</span></span>  

 <span data-ttu-id="86998-113">La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="86998-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="86998-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="86998-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="86998-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="86998-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="86998-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="86998-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="86998-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="86998-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="86998-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86998-118">See also</span></span>

- [<span data-ttu-id="86998-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="86998-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
