---
description: 'Más información acerca de: > (mayor que) (Entity SQL)'
title: '>  (Mayor que) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: e14470d477336fd719bb419657af3fdadcd54d98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786295"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="4e33e-103">> (mayor que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4e33e-103">> (Greater Than) (Entity SQL)</span></span>

<span data-ttu-id="4e33e-104">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="4e33e-104">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e33e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e33e-105">Syntax</span></span>  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e33e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4e33e-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="4e33e-107">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="4e33e-107">Any valid expression.</span></span> <span data-ttu-id="4e33e-108">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="4e33e-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4e33e-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="4e33e-109">Result Types</span></span>  

 <span data-ttu-id="4e33e-110">`true` si la expresión izquierda tiene un valor mayor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4e33e-110">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e33e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e33e-111">Example</span></span>  

 <span data-ttu-id="4e33e-112">La consulta de Entity SQL siguiente utiliza el operador de comparación > para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor mayor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="4e33e-112">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="4e33e-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="4e33e-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4e33e-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4e33e-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4e33e-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4e33e-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4e33e-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4e33e-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="4e33e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e33e-117">See also</span></span>

- [<span data-ttu-id="4e33e-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4e33e-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
