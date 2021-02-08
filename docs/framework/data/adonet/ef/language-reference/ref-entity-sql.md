---
description: 'Más información acerca de: REF (Entity SQL)'
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 05f87ce8027e8e095722eb13d39f3f13d56f6faa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802065"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="f381b-103">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f381b-103">REF (Entity SQL)</span></span>

<span data-ttu-id="f381b-104">Devuelve una referencia a una instancia de entidad.</span><span class="sxs-lookup"><span data-stu-id="f381b-104">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f381b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f381b-105">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="f381b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f381b-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="f381b-107">Cualquier expresión válida que produzca una instancia de un tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="f381b-107">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f381b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f381b-108">Return Value</span></span>  

 <span data-ttu-id="f381b-109">Referencia a la instancia de la entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="f381b-109">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f381b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f381b-110">Remarks</span></span>  

 <span data-ttu-id="f381b-111">La referencia a una entidad está compuesta de la clave de entidad y de un nombre de conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="f381b-111">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="f381b-112">Dado que diferentes conjuntos de entidades pueden basarse en el mismo tipo de entidad, una clave de entidad en particular podría aparecer en varios conjuntos de entidades.</span><span class="sxs-lookup"><span data-stu-id="f381b-112">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="f381b-113">Sin embargo, una referencia a entidad siempre es única.</span><span class="sxs-lookup"><span data-stu-id="f381b-113">However, an entity reference is always unique.</span></span> <span data-ttu-id="f381b-114">Si la expresión de entrada representa una entidad conservada, se devolverá una referencia a esta entidad.</span><span class="sxs-lookup"><span data-stu-id="f381b-114">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="f381b-115">Si la expresión de entrada no es una entidad conservada, se devolverá una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="f381b-115">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="f381b-116">Si el operador de extracción de propiedad (.) se usa para tener acceso a una propiedad de una entidad, las referencias de un valor de referencia se desreferencian automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f381b-116">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f381b-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f381b-117">Example</span></span>  

 <span data-ttu-id="f381b-118">La consulta de Entity SQL siguiente utiliza el operador REF para devolver la referencia para un argumento de entidad de entrada.</span><span class="sxs-lookup"><span data-stu-id="f381b-118">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="f381b-119">La misma consulta desreferencia la referencia porque se usa un operador de extracción de propiedad (.) para tener acceso a una propiedad de la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="f381b-119">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="f381b-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f381b-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f381b-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f381b-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f381b-122">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f381b-122">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f381b-123">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f381b-123">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="f381b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f381b-124">See also</span></span>

- [<span data-ttu-id="f381b-125">DEREF</span><span class="sxs-lookup"><span data-stu-id="f381b-125">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="f381b-126">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="f381b-126">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="f381b-127">KEY</span><span class="sxs-lookup"><span data-stu-id="f381b-127">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="f381b-128">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f381b-128">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f381b-129">Definiciones de tipos</span><span class="sxs-lookup"><span data-stu-id="f381b-129">Type Definitions</span></span>](type-definitions-entity-sql.md)
