---
description: Más información acerca de:-(negativo) (Entity SQL)
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: f3d30ce36b95e44755d148dc06279f67f15b0664
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712888"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="eaef8-103">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eaef8-103">- (Negative) (Entity SQL)</span></span>

<span data-ttu-id="eaef8-104">Devuelve el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="eaef8-104">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaef8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaef8-105">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="eaef8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eaef8-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="eaef8-107">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="eaef8-107">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="eaef8-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="eaef8-108">Result Types</span></span>  

 <span data-ttu-id="eaef8-109">El tipo de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="eaef8-109">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaef8-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eaef8-110">Remarks</span></span>  

 <span data-ttu-id="eaef8-111">Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="eaef8-111">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="eaef8-112">Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="eaef8-112">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaef8-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eaef8-113">Example</span></span>  

 <span data-ttu-id="eaef8-114">La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="eaef8-114">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="eaef8-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="eaef8-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="eaef8-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eaef8-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="eaef8-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="eaef8-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="eaef8-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="eaef8-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="eaef8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaef8-119">See also</span></span>

- [<span data-ttu-id="eaef8-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="eaef8-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
