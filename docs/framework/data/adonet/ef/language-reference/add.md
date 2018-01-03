---
title: + (Agregar)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: abd5921653e65c69da99a1aff60506aafd814278
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="-add"></a><span data-ttu-id="ac614-102">+ (Sumar)</span><span class="sxs-lookup"><span data-stu-id="ac614-102">+ (Add)</span></span>
<span data-ttu-id="ac614-103">Suma dos números.</span><span class="sxs-lookup"><span data-stu-id="ac614-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac614-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac614-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac614-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ac614-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ac614-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="ac614-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ac614-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ac614-107">Result Types</span></span>  
 <span data-ttu-id="ac614-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="ac614-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ac614-109">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ac614-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac614-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac614-110">Remarks</span></span>  
 <span data-ttu-id="ac614-111">Para los tipos EDM.String, la suma es una concatenación.</span><span class="sxs-lookup"><span data-stu-id="ac614-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac614-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac614-112">Example</span></span>  
 <span data-ttu-id="ac614-113">La siguiente consulta de Entity SQL usa el operador aritmético +  para sumar dos números.</span><span class="sxs-lookup"><span data-stu-id="ac614-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="ac614-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ac614-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ac614-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ac614-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ac614-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ac614-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ac614-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ac614-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="ac614-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac614-118">See Also</span></span>  
 [<span data-ttu-id="ac614-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ac614-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="ac614-120">Tipos de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ac614-120">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
