---
title: Problemas conocidos y consideraciones en LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: e84319c60534c3ecf154c3f58973bcc429a73842
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539820"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="c68d9-102">Problemas conocidos y consideraciones en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c68d9-102">Known Issues and Considerations in LINQ to Entities</span></span>
<span data-ttu-id="c68d9-103">Esta sección proporciona información sobre problemas conocidos con LINQ a consultas de entidades.</span><span class="sxs-lookup"><span data-stu-id="c68d9-103">This section provides information about known issues with LINQ to Entities queries.</span></span>  
  
- [<span data-ttu-id="c68d9-104">Consultas LINQ que no se puede almacenar en caché</span><span class="sxs-lookup"><span data-stu-id="c68d9-104">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
- [<span data-ttu-id="c68d9-105">Pérdida de información de ordenación</span><span class="sxs-lookup"><span data-stu-id="c68d9-105">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
- [<span data-ttu-id="c68d9-106">Enteros sin signo no admitidos</span><span class="sxs-lookup"><span data-stu-id="c68d9-106">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
- [<span data-ttu-id="c68d9-107">Errores de conversión de tipo</span><span class="sxs-lookup"><span data-stu-id="c68d9-107">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
- [<span data-ttu-id="c68d9-108">Hacer referencia a Variables no escalares no admitidas</span><span class="sxs-lookup"><span data-stu-id="c68d9-108">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
- [<span data-ttu-id="c68d9-109">Pueden producir un error de las consultas anidadas con SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="c68d9-109">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
- [<span data-ttu-id="c68d9-110">Proyectar un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="c68d9-110">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="c68d9-111">Consultas LINQ que no se pueden almacenar en memoria caché</span><span class="sxs-lookup"><span data-stu-id="c68d9-111">LINQ Queries That cannot be Cached</span></span>  
 <span data-ttu-id="c68d9-112">A partir de .NET Framework 4.0.5, las consultas LINQ to Entities se almacenan automáticamente en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c68d9-112">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="c68d9-113">Sin embargo, as consultas LINQ to Entities que aplican el operador `Enumerable.Contains` a colecciones en memoria no se almacenan en memoria caché automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c68d9-113">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="c68d9-114">Tampoco se permite parametrizar colecciones en memoria en consultas LINQ compiladas.</span><span class="sxs-lookup"><span data-stu-id="c68d9-114">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a><span data-ttu-id="c68d9-115">Pérdida de información de ordenación</span><span class="sxs-lookup"><span data-stu-id="c68d9-115">Ordering Information Lost</span></span>  
 <span data-ttu-id="c68d9-116">La proyección de columnas en un tipo anónimo provocará la pérdida de información de ordenación en algunas consultas que se ejecuten en un conjunto de base de datos de [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] con un nivel de la compatibilidad de "80".</span><span class="sxs-lookup"><span data-stu-id="c68d9-116">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] database set to a compatibility level of "80".</span></span>  <span data-ttu-id="c68d9-117">Esto se produce cuando un nombre de columna en la lista ORDER BY coincide con un nombre de columna en el selector, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c68d9-117">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="c68d9-118">Enteros sin signo no admitidos</span><span class="sxs-lookup"><span data-stu-id="c68d9-118">Unsigned Integers Not Supported</span></span>  
 <span data-ttu-id="c68d9-119">No se admite la especificación de un tipo entero sin signo en una consulta LINQ to Entities porque el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] no admite enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="c68d9-119">Specifying an unsigned integer type in a LINQ to Entities query is not supported because the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not support unsigned integers.</span></span> <span data-ttu-id="c68d9-120">Si especifica un entero sin signo, un <xref:System.ArgumentException> excepción se producirá durante la conversión de expresión de consulta, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c68d9-120">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="c68d9-121">En este ejemplo se consulta un pedido cuyo número de identificación (Id.) es 48000.</span><span class="sxs-lookup"><span data-stu-id="c68d9-121">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a><span data-ttu-id="c68d9-122">Errores de la conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="c68d9-122">Type Conversion Errors</span></span>  
 <span data-ttu-id="c68d9-123">En Visual Basic, cuando se asigna una propiedad a una columna de tipo bit de SQL Server con un valor de 1 utilizando la función `CByte`, se produce una excepción <xref:System.Data.SqlClient.SqlException> con el mensaje "Error de desbordamiento aritmético".</span><span class="sxs-lookup"><span data-stu-id="c68d9-123">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="c68d9-124">En el ejemplo siguiente se consulta la columna `Product.MakeFlag` en la base de datos de ejemplo AdventureWorks y se produce una excepción cuando tiene lugar una iteración en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c68d9-124">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="c68d9-125">Referencia a variables no escalares no admitida</span><span class="sxs-lookup"><span data-stu-id="c68d9-125">Referencing Non-Scalar Variables Not Supported</span></span>  
 <span data-ttu-id="c68d9-126">En una consulta no se puede hacer referencia a variables no escalares, tales como una entidad.</span><span class="sxs-lookup"><span data-stu-id="c68d9-126">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="c68d9-127">Cuando este tipo de consulta se ejecuta, se genera una excepción <xref:System.NotSupportedException> con un mensaje que indica "No se puede crear un valor constante de tipo `EntityType`".</span><span class="sxs-lookup"><span data-stu-id="c68d9-127">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="c68d9-128">Sólo los tipos primitivos ('como Int32, String y Guid') se admiten en este contexto.".</span><span class="sxs-lookup"><span data-stu-id="c68d9-128">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c68d9-129">Permite hacer referencia a una colección de variables escalares.</span><span class="sxs-lookup"><span data-stu-id="c68d9-129">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="c68d9-130">Se puede producir un error en consultas anidadas con SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="c68d9-130">Nested Queries May Fail with SQL Server 2000</span></span>  
 <span data-ttu-id="c68d9-131">Con SQL Server 2000, se puede producir un error en consultas LINQ to Entities si se generan consultas Transact-SQL anidadas con tres o más niveles de profundidad.</span><span class="sxs-lookup"><span data-stu-id="c68d9-131">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="c68d9-132">Proyectar a un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="c68d9-132">Projecting to an Anonymous Type</span></span>  
 <span data-ttu-id="c68d9-133">Si define su ruta de acceso de consultas inicial para incluir objetos relacionados utilizando el método <xref:System.Data.Objects.ObjectQuery%601.Include%2A> sobre <xref:System.Data.Objects.ObjectQuery%601> y, a continuación, utiliza LINQ para proyectar los objetos devueltos sobre un tipo anónimo, los objetos especificados en el método de inclusión no se incluyen en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c68d9-133">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="c68d9-134">Para obtener objetos relacionados, no proyecte los tipos devueltos sobre un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="c68d9-134">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="c68d9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c68d9-135">See also</span></span>

- [<span data-ttu-id="c68d9-136">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c68d9-136">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
