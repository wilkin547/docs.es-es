---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 05e687f951930d92797a863410181585278b067d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330667"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="6ff82-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6ff82-102">REF (Entity SQL)</span></span>
<span data-ttu-id="6ff82-103">Devuelve una referencia a una instancia de entidad.</span><span class="sxs-lookup"><span data-stu-id="6ff82-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ff82-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="6ff82-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ff82-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6ff82-106">Cualquier expresión válida que produzca una instancia de un tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="6ff82-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ff82-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ff82-107">Return Value</span></span>  
 <span data-ttu-id="6ff82-108">Referencia a la instancia de la entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="6ff82-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ff82-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ff82-109">Remarks</span></span>  
 <span data-ttu-id="6ff82-110">La referencia a una entidad está compuesta de la clave de entidad y de un nombre de conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="6ff82-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="6ff82-111">Dado que diferentes conjuntos de entidades pueden basarse en el mismo tipo de entidad, una clave de entidad en particular podría aparecer en varios conjuntos de entidades.</span><span class="sxs-lookup"><span data-stu-id="6ff82-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="6ff82-112">Sin embargo, una referencia a entidad siempre es única.</span><span class="sxs-lookup"><span data-stu-id="6ff82-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="6ff82-113">Si la expresión de entrada representa una entidad conservada, se devolverá una referencia a esta entidad.</span><span class="sxs-lookup"><span data-stu-id="6ff82-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="6ff82-114">Si la expresión de entrada no es una entidad conservada, se devolverá una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="6ff82-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="6ff82-115">Si el operador de extracción de propiedad (.) se usa para tener acceso a una propiedad de una entidad, las referencias de un valor de referencia se desreferencian automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6ff82-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ff82-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ff82-116">Example</span></span>  
 <span data-ttu-id="6ff82-117">La consulta de Entity SQL siguiente utiliza el operador REF para devolver la referencia para un argumento de entidad de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ff82-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="6ff82-118">La misma consulta desreferencia la referencia porque se usa un operador de extracción de propiedad (.) para tener acceso a una propiedad de la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="6ff82-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="6ff82-119">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6ff82-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6ff82-120">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ff82-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6ff82-121">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6ff82-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="6ff82-122">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6ff82-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="6ff82-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ff82-123">See also</span></span>

- [<span data-ttu-id="6ff82-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="6ff82-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [<span data-ttu-id="6ff82-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="6ff82-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="6ff82-126">KEY</span><span class="sxs-lookup"><span data-stu-id="6ff82-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="6ff82-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6ff82-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6ff82-128">Definiciones de tipos</span><span class="sxs-lookup"><span data-stu-id="6ff82-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
