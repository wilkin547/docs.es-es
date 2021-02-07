---
description: 'Más información sobre: problemas conocidos y consideraciones en LINQ to Entities'
title: Problemas conocidos y consideraciones en LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 61377fc27770cb16583e0347fff1a03b6cd44af6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748315"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="af8db-103">Problemas conocidos y consideraciones en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="af8db-103">Known Issues and Considerations in LINQ to Entities</span></span>

<span data-ttu-id="af8db-104">En esta sección se proporciona información sobre los problemas conocidos de las consultas de LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="af8db-104">This section provides information about known issues with LINQ to Entities queries.</span></span>  
  
- [<span data-ttu-id="af8db-105">Consultas LINQ que no se pueden almacenar en memoria caché</span><span class="sxs-lookup"><span data-stu-id="af8db-105">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
- [<span data-ttu-id="af8db-106">Pérdida de información de ordenación</span><span class="sxs-lookup"><span data-stu-id="af8db-106">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
- [<span data-ttu-id="af8db-107">Enteros sin signo no admitidos</span><span class="sxs-lookup"><span data-stu-id="af8db-107">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
- [<span data-ttu-id="af8db-108">Errores de la conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="af8db-108">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
- [<span data-ttu-id="af8db-109">Referencia a variables no escalares no admitida</span><span class="sxs-lookup"><span data-stu-id="af8db-109">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
- [<span data-ttu-id="af8db-110">Se puede producir un error en consultas anidadas con SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="af8db-110">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
- [<span data-ttu-id="af8db-111">Proyectar a un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="af8db-111">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>

## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="af8db-112">Consultas LINQ que no se pueden almacenar en memoria caché</span><span class="sxs-lookup"><span data-stu-id="af8db-112">LINQ Queries That cannot be Cached</span></span>  

 <span data-ttu-id="af8db-113">A partir de .NET Framework 4.0.5, las consultas LINQ to Entities se almacenan automáticamente en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="af8db-113">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="af8db-114">Sin embargo, as consultas LINQ to Entities que aplican el operador `Enumerable.Contains` a colecciones en memoria no se almacenan en memoria caché automáticamente.</span><span class="sxs-lookup"><span data-stu-id="af8db-114">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="af8db-115">Tampoco se permite parametrizar colecciones en memoria en consultas LINQ compiladas.</span><span class="sxs-lookup"><span data-stu-id="af8db-115">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>

## <a name="ordering-information-lost"></a><span data-ttu-id="af8db-116">Pérdida de información de ordenación</span><span class="sxs-lookup"><span data-stu-id="af8db-116">Ordering Information Lost</span></span>  

 <span data-ttu-id="af8db-117">La proyección de columnas en un tipo anónimo hará que se pierda información de ordenación en algunas consultas que se ejecutan en una base de datos SQL Server 2005 establecida en un nivel de compatibilidad de "80".</span><span class="sxs-lookup"><span data-stu-id="af8db-117">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a SQL Server 2005 database set to a compatibility level of "80".</span></span>  <span data-ttu-id="af8db-118">Esto se produce cuando un nombre de columna en la lista ORDER BY coincide con un nombre de columna en el selector, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af8db-118">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>

## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="af8db-119">Enteros sin signo no admitidos</span><span class="sxs-lookup"><span data-stu-id="af8db-119">Unsigned Integers Not Supported</span></span>  

 <span data-ttu-id="af8db-120">No se admite la especificación de un tipo entero sin signo en una consulta de LINQ to Entities porque el Entity Framework no admite enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="af8db-120">Specifying an unsigned integer type in a LINQ to Entities query is not supported because the Entity Framework does not support unsigned integers.</span></span> <span data-ttu-id="af8db-121">Si especifica un entero sin signo, se <xref:System.ArgumentException> producirá una excepción durante la traducción de la expresión de consulta, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="af8db-121">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="af8db-122">En este ejemplo se consulta un pedido cuyo número de identificación (Id.) es 48000.</span><span class="sxs-lookup"><span data-stu-id="af8db-122">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>

## <a name="type-conversion-errors"></a><span data-ttu-id="af8db-123">Errores de la conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="af8db-123">Type Conversion Errors</span></span>  

 <span data-ttu-id="af8db-124">En Visual Basic, cuando se asigna una propiedad a una columna de tipo bit de SQL Server con un valor de 1 utilizando la función `CByte`, se produce una excepción <xref:System.Data.SqlClient.SqlException> con el mensaje "Error de desbordamiento aritmético".</span><span class="sxs-lookup"><span data-stu-id="af8db-124">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="af8db-125">En el ejemplo siguiente se consulta la columna `Product.MakeFlag` en la base de datos de ejemplo AdventureWorks y se produce una excepción cuando tiene lugar una iteración en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="af8db-125">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>

## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="af8db-126">Referencia a variables no escalares no admitida</span><span class="sxs-lookup"><span data-stu-id="af8db-126">Referencing Non-Scalar Variables Not Supported</span></span>  

 <span data-ttu-id="af8db-127">En una consulta no se puede hacer referencia a variables no escalares, tales como una entidad.</span><span class="sxs-lookup"><span data-stu-id="af8db-127">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="af8db-128">Cuando este tipo de consulta se ejecuta, se genera una excepción <xref:System.NotSupportedException> con un mensaje que indica "No se puede crear un valor constante de tipo `EntityType`".</span><span class="sxs-lookup"><span data-stu-id="af8db-128">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="af8db-129">Sólo los tipos primitivos ('como Int32, String y Guid') se admiten en este contexto.".</span><span class="sxs-lookup"><span data-stu-id="af8db-129">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af8db-130">Permite hacer referencia a una colección de variables escalares.</span><span class="sxs-lookup"><span data-stu-id="af8db-130">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>

## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="af8db-131">Se puede producir un error en consultas anidadas con SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="af8db-131">Nested Queries May Fail with SQL Server 2000</span></span>  

 <span data-ttu-id="af8db-132">Con SQL Server 2000, se puede producir un error en consultas LINQ to Entities si se generan consultas Transact-SQL anidadas con tres o más niveles de profundidad.</span><span class="sxs-lookup"><span data-stu-id="af8db-132">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>

## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="af8db-133">Proyectar a un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="af8db-133">Projecting to an Anonymous Type</span></span>  

 <span data-ttu-id="af8db-134">Si define su ruta de acceso de consultas inicial para incluir objetos relacionados utilizando el método <xref:System.Data.Objects.ObjectQuery%601.Include%2A> sobre <xref:System.Data.Objects.ObjectQuery%601> y, a continuación, utiliza LINQ para proyectar los objetos devueltos sobre un tipo anónimo, los objetos especificados en el método de inclusión no se incluyen en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="af8db-134">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="af8db-135">Para obtener objetos relacionados, no proyecte los tipos devueltos sobre un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="af8db-135">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="af8db-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="af8db-136">See also</span></span>

- [<span data-ttu-id="af8db-137">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="af8db-137">LINQ to Entities</span></span>](linq-to-entities.md)
