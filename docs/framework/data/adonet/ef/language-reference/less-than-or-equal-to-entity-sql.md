---
title: <= (menor o igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 09f2a7f53d00739b8542cb1149397f24d3b04f42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161807"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="b57a7-102">\<= (Menor o igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b57a7-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>

<span data-ttu-id="b57a7-103">Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="b57a7-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b57a7-104">Syntax</span></span>  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b57a7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b57a7-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="b57a7-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="b57a7-106">Any valid expression.</span></span> <span data-ttu-id="b57a7-107">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="b57a7-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b57a7-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b57a7-108">Result Types</span></span>  

 <span data-ttu-id="b57a7-109">`true` si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b57a7-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b57a7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b57a7-110">Example</span></span>  

 <span data-ttu-id="b57a7-111">La consulta de Entity SQL siguiente utiliza el operador de comparación <= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="b57a7-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="b57a7-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b57a7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b57a7-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b57a7-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b57a7-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b57a7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b57a7-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b57a7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="b57a7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b57a7-116">See also</span></span>

- [<span data-ttu-id="b57a7-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b57a7-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
