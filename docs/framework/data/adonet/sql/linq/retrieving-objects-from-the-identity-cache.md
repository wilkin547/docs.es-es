---
description: Más información acerca de cómo recuperar objetos de la memoria caché de identidades
title: Recuperar objetos de la memoria caché de identidades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 1f3d5f839a6fff33d62d4e0cb2281bd087f2d320
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695091"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="7302c-103">Recuperar objetos de la memoria caché de identidades</span><span class="sxs-lookup"><span data-stu-id="7302c-103">Retrieving Objects from the Identity Cache</span></span>

<span data-ttu-id="7302c-104">En este tema se describen los tipos de consultas LINQ to SQL que devuelven un objeto desde la memoria caché de identidad que está administrado por el <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="7302c-104">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="7302c-105">En LINQ to SQL, una de las formas en que <xref:System.Data.Linq.DataContext> administra los objetos consiste en registrar identidades de objetos en una memoria caché de identidad a medida que se ejecutan consultas.</span><span class="sxs-lookup"><span data-stu-id="7302c-105">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="7302c-106">En algunos casos, LINQ to SQL intentará recuperar un objeto desde la memoria caché de identidad antes de ejecutar una consulta en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7302c-106">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="7302c-107">En general, para que una consulta LINQ to SQL devuelva un objeto desde la memoria caché de identidad, la consulta debe estar basada en la clave principal de un objeto y debe devolver un único objeto.</span><span class="sxs-lookup"><span data-stu-id="7302c-107">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="7302c-108">En particular, la consulta debe estar en uno de los formatos generales indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="7302c-108">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7302c-109">Las consultas precompiladas no devolverán objetos desde la memoria caché de identidad.</span><span class="sxs-lookup"><span data-stu-id="7302c-109">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="7302c-110">Para obtener más información acerca de las consultas compiladas previamente, vea <xref:System.Data.Linq.CompiledQuery> y [Cómo: almacenar y reutilizar consultas](how-to-store-and-reuse-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7302c-110">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="7302c-111">Para recuperar un objeto de la memoria caché de identidad, una consulta debe tener uno de los formatos generales siguientes:</span><span class="sxs-lookup"><span data-stu-id="7302c-111">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
- <span data-ttu-id="7302c-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="7302c-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
- <span data-ttu-id="7302c-113"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="7302c-113"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="7302c-114">En estos formatos generales, `Function1`, `Function2` y `predicate` se definen como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="7302c-114">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="7302c-115">`Function1` puede ser de cualquiera de las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7302c-115">`Function1` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="7302c-116">`Function2` puede ser de cualquiera de las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7302c-116">`Function2` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="7302c-117">`predicate` debe ser una expresión en la que la propiedad de la clave principal del objeto está establecida en un valor constante.</span><span class="sxs-lookup"><span data-stu-id="7302c-117">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="7302c-118">Si un objeto tiene una clave principal definida mediante más de una propiedad, cada una de estas propiedades debe estar establecida en un valor constante.</span><span class="sxs-lookup"><span data-stu-id="7302c-118">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="7302c-119">A continuación, se ofrecen ejemplos del formato que debe tener `predicate`:</span><span class="sxs-lookup"><span data-stu-id="7302c-119">The following are examples of the form `predicate` must take:</span></span>  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="7302c-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7302c-120">Example</span></span>  

 <span data-ttu-id="7302c-121">El código siguiente proporciona ejemplos de los tipos de consultas LINQ to SQL que recuperan un objeto desde la memoria caché de identidad.</span><span class="sxs-lookup"><span data-stu-id="7302c-121">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7302c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7302c-122">See also</span></span>

- [<span data-ttu-id="7302c-123">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="7302c-123">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="7302c-124">Identidad de objetos</span><span class="sxs-lookup"><span data-stu-id="7302c-124">Object Identity</span></span>](object-identity.md)
- [<span data-ttu-id="7302c-125">Información general</span><span class="sxs-lookup"><span data-stu-id="7302c-125">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="7302c-126">Identidad de objetos</span><span class="sxs-lookup"><span data-stu-id="7302c-126">Object Identity</span></span>](object-identity.md)
