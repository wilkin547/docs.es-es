---
title: '&gt;= (Mayor o igual que) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b176e1efdc17b58083234d0437033bd43775f604
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="31d05-102">&gt;= (Mayor o igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="31d05-102">&gt;= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="31d05-103">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor igual o mayor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="31d05-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31d05-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="31d05-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="31d05-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="31d05-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="31d05-106">Any valid expression.</span></span> <span data-ttu-id="31d05-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="31d05-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="31d05-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="31d05-108">Result Types</span></span>  
 <span data-ttu-id="31d05-109">`true` si la expresión izquierda tiene un valor igual o mayor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="31d05-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31d05-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31d05-110">Example</span></span>  
 <span data-ttu-id="31d05-111">La consulta de Entity SQL siguiente utiliza el operador de comparación >= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o mayor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="31d05-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="31d05-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="31d05-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="31d05-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31d05-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="31d05-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="31d05-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="31d05-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="31d05-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="31d05-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="31d05-116">See Also</span></span>  
 [<span data-ttu-id="31d05-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="31d05-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
