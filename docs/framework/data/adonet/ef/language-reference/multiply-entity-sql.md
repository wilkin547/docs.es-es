---
title: '* (Multiplicar) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c7e2bcf15ab8d0cf24fdc6cb7e9db025784bd435
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="5c65a-102">\* (Multiplicar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5c65a-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="5c65a-103">Multiplica dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="5c65a-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c65a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c65a-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c65a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5c65a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5c65a-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="5c65a-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5c65a-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="5c65a-107">Result Types</span></span>  
 <span data-ttu-id="5c65a-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="5c65a-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="5c65a-109">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5c65a-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c65a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c65a-110">Example</span></span>  
 <span data-ttu-id="5c65a-111">La siguiente consulta de Entity SQL usa el operador aritmético \* para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="5c65a-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="5c65a-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5c65a-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5c65a-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5c65a-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5c65a-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5c65a-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5c65a-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5c65a-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="5c65a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c65a-116">See Also</span></span>  
 [<span data-ttu-id="5c65a-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5c65a-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
