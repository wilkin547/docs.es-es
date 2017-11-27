---
title: '&lt;= (Menor o igual que) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6b3e6054233074010f46d28e1c5b15d456ae41bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lt-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="c1125-102">&lt;= (Menor o igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c1125-102">&lt;= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="c1125-103">Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="c1125-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1125-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1125-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1125-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c1125-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c1125-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="c1125-106">Any valid expression.</span></span> <span data-ttu-id="c1125-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="c1125-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c1125-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c1125-108">Result Types</span></span>  
 <span data-ttu-id="c1125-109">`true` si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c1125-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1125-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1125-110">Example</span></span>  
 <span data-ttu-id="c1125-111">La consulta de Entity SQL siguiente utiliza el operador de comparación <= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="c1125-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="c1125-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c1125-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c1125-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c1125-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c1125-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c1125-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c1125-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c1125-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="c1125-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1125-116">See Also</span></span>  
 [<span data-ttu-id="c1125-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c1125-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
