---
title: MULTISET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e72605225d214ccd2283aaae3f0c2071ceb92d91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="5dcaa-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5dcaa-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="5dcaa-103">Crea una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="5dcaa-104">Todos los valores en el constructor MULTISET deben ser de un tipo `T`compatible.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="5dcaa-105">No se permiten los constructores MULTISET vacíos.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dcaa-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dcaa-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="5dcaa-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5dcaa-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5dcaa-108">Cualquier lista válida de valores.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dcaa-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5dcaa-109">Return Value</span></span>  
 <span data-ttu-id="5dcaa-110">Una colección de tipo MULTISET\<T >.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dcaa-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5dcaa-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5dcaa-112"> proporciona tres tipos de constructores: los constructores ROW, los constructores de objeto y los constructores MULTISET (o colección).</span><span class="sxs-lookup"><span data-stu-id="5dcaa-112"> provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="5dcaa-113">Para obtener más información, consulte [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5dcaa-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="5dcaa-114">El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="5dcaa-115">Todos los valores en el constructor deben ser de un tipo compatible.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="5dcaa-116">Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="5dcaa-117">Solo se admiten los literales de conjunto múltiple anidados cuando un conjunto múltiple contenedor tiene un único elemento de conjunto múltiple; por ejemplo, `{{1, 2, 3}}`.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-117">Nested multiset literals are only supported when a wrapping mutiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="5dcaa-118">Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dcaa-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dcaa-119">Example</span></span>  
 <span data-ttu-id="5dcaa-120">La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="5dcaa-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5dcaa-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5dcaa-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5dcaa-123">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5dcaa-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5dcaa-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5dcaa-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="5dcaa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dcaa-125">See Also</span></span>  
 [<span data-ttu-id="5dcaa-126">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="5dcaa-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="5dcaa-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5dcaa-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
