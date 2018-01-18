---
title: '- (Negativo) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2ceedd99221047ab73474ad5dc2478e527618b87
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="beb5c-102">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="beb5c-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="beb5c-103">Devuelve el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="beb5c-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beb5c-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="beb5c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="beb5c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="beb5c-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="beb5c-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="beb5c-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="beb5c-107">Result Types</span></span>  
 <span data-ttu-id="beb5c-108">Tipo de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="beb5c-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb5c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="beb5c-109">Remarks</span></span>  
 <span data-ttu-id="beb5c-110">Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="beb5c-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="beb5c-111">Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="beb5c-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb5c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="beb5c-112">Example</span></span>  
 <span data-ttu-id="beb5c-113">La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="beb5c-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="beb5c-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="beb5c-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="beb5c-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="beb5c-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="beb5c-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="beb5c-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="beb5c-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="beb5c-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="beb5c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="beb5c-118">See Also</span></span>  
 [<span data-ttu-id="beb5c-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="beb5c-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
