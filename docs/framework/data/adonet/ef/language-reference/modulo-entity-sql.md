---
description: 'Más información acerca de: (módulo) (Entity SQL)'
title: (Módulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 8ac9bf2fa9dbee843215dcfeed13fefc7bd54796
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696638"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="319d5-103">(Módulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="319d5-103">(Modulo) (Entity SQL)</span></span>

<span data-ttu-id="319d5-104">Devuelve el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="319d5-104">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="319d5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="319d5-105">Syntax</span></span>  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="319d5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="319d5-106">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="319d5-107">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="319d5-107">The numeric expression to divide.</span></span> <span data-ttu-id="319d5-108">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="319d5-108">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="319d5-109">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="319d5-109">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="319d5-110">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="319d5-110">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="319d5-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="319d5-111">Result Types</span></span>  

 <span data-ttu-id="319d5-112">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="319d5-112">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="319d5-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="319d5-113">Example</span></span>  

 <span data-ttu-id="319d5-114">La siguiente consulta de Entity SQL usa el operador aritmético % para devolver el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="319d5-114">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="319d5-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="319d5-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="319d5-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="319d5-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="319d5-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="319d5-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="319d5-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="319d5-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="319d5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="319d5-119">See also</span></span>

- [<span data-ttu-id="319d5-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="319d5-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
