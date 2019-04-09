---
title: < = (menor o igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 9e5a61cb68895982344eadec083a697bdaff54e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193959"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="1d4d7-102">\<= (Menor o igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1d4d7-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="1d4d7-103">Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d4d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d4d7-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d4d7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1d4d7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1d4d7-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-106">Any valid expression.</span></span> <span data-ttu-id="1d4d7-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1d4d7-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1d4d7-108">Result Types</span></span>  
 `true` <span data-ttu-id="1d4d7-109">Si la expresión izquierda tiene un valor menor o igual a la expresión derecha; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-109">if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d4d7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d4d7-110">Example</span></span>  
 <span data-ttu-id="1d4d7-111">La consulta de Entity SQL siguiente utiliza el operador de comparación <= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="1d4d7-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1d4d7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1d4d7-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1d4d7-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1d4d7-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1d4d7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1d4d7-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1d4d7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="1d4d7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d4d7-116">See also</span></span>

- [<span data-ttu-id="1d4d7-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1d4d7-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
