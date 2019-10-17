---
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 7716b9115587a873531be9c14b7da93c7a148ed8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319536"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="16ea4-102">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="16ea4-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="16ea4-103">Devuelve el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="16ea4-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ea4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16ea4-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="16ea4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="16ea4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="16ea4-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="16ea4-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="16ea4-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="16ea4-107">Result Types</span></span>  
 <span data-ttu-id="16ea4-108">Tipo de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="16ea4-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16ea4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16ea4-109">Remarks</span></span>  
 <span data-ttu-id="16ea4-110">Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="16ea4-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="16ea4-111">Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="16ea4-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16ea4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16ea4-112">Example</span></span>  
 <span data-ttu-id="16ea4-113">La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="16ea4-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="16ea4-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="16ea4-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="16ea4-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="16ea4-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="16ea4-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="16ea4-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="16ea4-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="16ea4-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="16ea4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="16ea4-118">See also</span></span>

- [<span data-ttu-id="16ea4-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="16ea4-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
