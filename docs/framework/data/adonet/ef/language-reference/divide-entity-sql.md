---
description: Más información acerca de:/(dividir) (Entity SQL)
title: '- Dividir (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 4ac487c636c460401eeb147dc7ce1a8d8ba7f7ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724640"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="bf5a1-103">/ (Dividir) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bf5a1-103">/ (Divide) (Entity SQL)</span></span>

<span data-ttu-id="bf5a1-104">Divide un número por otro.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-104">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf5a1-105">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf5a1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bf5a1-106">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="bf5a1-107">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-107">The numeric expression to divide.</span></span> <span data-ttu-id="bf5a1-108">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-108">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="bf5a1-109">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-109">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="bf5a1-110">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-110">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bf5a1-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="bf5a1-111">Result Types</span></span>  

 <span data-ttu-id="bf5a1-112">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-112">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="bf5a1-113">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bf5a1-113">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf5a1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf5a1-114">Example</span></span>  

 <span data-ttu-id="bf5a1-115">La consulta de Entity SQL siguiente utiliza el operador aritmético/para dividir un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-115">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="bf5a1-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bf5a1-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bf5a1-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bf5a1-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bf5a1-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bf5a1-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bf5a1-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bf5a1-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="bf5a1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5a1-120">See also</span></span>

- [<span data-ttu-id="bf5a1-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bf5a1-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
