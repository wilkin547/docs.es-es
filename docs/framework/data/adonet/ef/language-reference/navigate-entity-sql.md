---
title: NAVIGATE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a860fae543e4d74e2b0569ed3672f3dc113f84c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="e6b49-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e6b49-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="e6b49-103">Navega por la relación establecida entre entidades.</span><span class="sxs-lookup"><span data-stu-id="e6b49-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6b49-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6b49-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e6b49-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="e6b49-106">Instancia de una entidad.</span><span class="sxs-lookup"><span data-stu-id="e6b49-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="e6b49-107">Nombre de tipo de la relación, del archivo de lenguaje de definición de esquemas conceptuales (CSDL).</span><span class="sxs-lookup"><span data-stu-id="e6b49-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="e6b49-108">El `relationship-type` se califica como \<espacio de nombres >.\< nombre de tipo de relación >.</span><span class="sxs-lookup"><span data-stu-id="e6b49-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="e6b49-109">Final de la relación.</span><span class="sxs-lookup"><span data-stu-id="e6b49-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="e6b49-110">Comienzo de la relación.</span><span class="sxs-lookup"><span data-stu-id="e6b49-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6b49-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6b49-111">Return Value</span></span>  
 <span data-ttu-id="e6b49-112">Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="e6b49-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="e6b49-113">Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="e6b49-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6b49-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6b49-114">Remarks</span></span>  
 <span data-ttu-id="e6b49-115">Las relaciones son estructuras de primera clase en [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span><span class="sxs-lookup"><span data-stu-id="e6b49-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="e6b49-116">Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo (entidad) al otro.</span><span class="sxs-lookup"><span data-stu-id="e6b49-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="e6b49-117">`from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.</span><span class="sxs-lookup"><span data-stu-id="e6b49-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="e6b49-118">NAVIGATE es válido en espacios O y C.</span><span class="sxs-lookup"><span data-stu-id="e6b49-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="e6b49-119">La forma general de una estructura de navegación es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6b49-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="e6b49-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="e6b49-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="e6b49-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6b49-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e6b49-122">Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` (cliente) y `from-end` (pedido) de la relación.</span><span class="sxs-lookup"><span data-stu-id="e6b49-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="e6b49-123">Si OrderCustomer es una relación de n: 1, el tipo de resultado de la expresión navigate es Ref\<Customer >.</span><span class="sxs-lookup"><span data-stu-id="e6b49-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="e6b49-124">Lo forma más simple de esta expresión es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6b49-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e6b49-125">De forma similar, en una consulta de la forma siguiente, la expresión navigate generaría una colección < Ref\<orden >>.</span><span class="sxs-lookup"><span data-stu-id="e6b49-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="e6b49-126">El valor de instance-expression debe ser de tipo entidad/referencia.</span><span class="sxs-lookup"><span data-stu-id="e6b49-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6b49-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6b49-127">Example</span></span>  
 <span data-ttu-id="e6b49-128">La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e6b49-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="e6b49-129">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e6b49-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e6b49-130">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6b49-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e6b49-131">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e6b49-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e6b49-132">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e6b49-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="e6b49-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6b49-133">See Also</span></span>  
 [<span data-ttu-id="e6b49-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e6b49-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e6b49-135">Cómo: navegar por relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="e6b49-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
