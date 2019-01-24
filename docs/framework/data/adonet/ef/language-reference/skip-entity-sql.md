---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 467329f74304b64c7fc7ada2920751aba744f76e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637643"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="f03a8-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f03a8-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="f03a8-103">Puede realizar la paginación física utilizando la subcláusula SKIP en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="f03a8-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="f03a8-104">SKIP no se puede utilizar por separado de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="f03a8-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f03a8-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f03a8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f03a8-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="f03a8-107">Número de elementos que se han de omitir.</span><span class="sxs-lookup"><span data-stu-id="f03a8-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f03a8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f03a8-108">Remarks</span></span>  
 <span data-ttu-id="f03a8-109">Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP.</span><span class="sxs-lookup"><span data-stu-id="f03a8-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="f03a8-110">Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.</span><span class="sxs-lookup"><span data-stu-id="f03a8-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f03a8-111">Una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se no es válida si tanto el modificador TOP como la subcláusula SKIP están presentes en la misma expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f03a8-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="f03a8-112">La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="f03a8-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f03a8-113">En [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], el uso de SKIP con ORDER BY en columnas sin clave puede hacer que los resultados devueltos sean incorrectos.</span><span class="sxs-lookup"><span data-stu-id="f03a8-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="f03a8-114">Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella.</span><span class="sxs-lookup"><span data-stu-id="f03a8-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="f03a8-115">Esto se debe a cómo se convierte SKIP en [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f03a8-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="f03a8-116">Por ejemplo, en el código siguiente se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:</span><span class="sxs-lookup"><span data-stu-id="f03a8-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="f03a8-117">La consulta de  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en [este](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) ejemplo, usa el operador ORDER BY con SKIP para especificar el criterio de ordenación que se usa en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="f03a8-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [this](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) example uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03a8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f03a8-118">See also</span></span>
- [<span data-ttu-id="f03a8-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f03a8-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [<span data-ttu-id="f03a8-120">Cómo: Página de resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="f03a8-120">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
- [<span data-ttu-id="f03a8-121">Paginación</span><span class="sxs-lookup"><span data-stu-id="f03a8-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="f03a8-122">TOP</span><span class="sxs-lookup"><span data-stu-id="f03a8-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
