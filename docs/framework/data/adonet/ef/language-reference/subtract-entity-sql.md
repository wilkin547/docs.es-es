---
title: '- (Restar) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5ca2bc8cb34d99421962289930c26de84eaa68e2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="ae8ce-102">- (Restar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ae8ce-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="ae8ce-103">Resta dos números.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae8ce-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae8ce-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ae8ce-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ae8ce-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ae8ce-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ae8ce-107">Result Types</span></span>  
 <span data-ttu-id="ae8ce-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ae8ce-109">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ae8ce-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae8ce-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae8ce-110">Example</span></span>  
 <span data-ttu-id="ae8ce-111">La siguiente consulta de Entity SQL usa el operador aritmético - para restar dos números.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="ae8ce-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ae8ce-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ae8ce-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ae8ce-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ae8ce-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ae8ce-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ae8ce-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="ae8ce-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae8ce-116">See Also</span></span>  
 [<span data-ttu-id="ae8ce-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ae8ce-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
