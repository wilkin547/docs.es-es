---
title: "Ejemplos de sintaxis de expresión de consulta: navegar por relaciones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d86fa3aab55daff9c7a3724c93ad68be27a6908b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="94ab8-102">Ejemplos de sintaxis de expresión de consulta: navegar por relaciones</span><span class="sxs-lookup"><span data-stu-id="94ab8-102">Query Expression Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="94ab8-103">Las propiedades de navegación de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] son propiedades de acceso directo que se emplean para localizar las entidades situadas en los extremos de una asociación.</span><span class="sxs-lookup"><span data-stu-id="94ab8-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="94ab8-104">Las propiedades de navegación permiten a un usuario navegar de una entidad a otra, o desde una entidad a entidades relacionadas a través de un conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="94ab8-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="94ab8-105">En este tema se ofrecen ejemplos de la sintaxis de las expresiones de consultas para navegar por las relaciones a través de propiedades de navegación de las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ab8-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="94ab8-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="94ab8-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="94ab8-107">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="94ab8-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="94ab8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ab8-108">Example</span></span>  
 <span data-ttu-id="94ab8-109">En el ejemplo siguiente se usa el método <xref:System.Linq.Queryable.Select%2A> para obtener todos los identificadores de contactos y la suma del importe total a pagar de cada contacto cuyo nombre sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="94ab8-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="94ab8-110">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="94ab8-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="94ab8-111">El método `Sum` usa la propiedad de navegación `Contact.SalesOrderHeader` para sumar el importe total a pagar de todos los pedidos de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="94ab8-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="94ab8-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ab8-112">Example</span></span>  
 <span data-ttu-id="94ab8-113">El ejemplo siguiente obtiene todos los pedidos de los contactos cuyo apellido sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="94ab8-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="94ab8-114">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="94ab8-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="94ab8-115">El nombre y los pedidos del contacto se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="94ab8-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="94ab8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ab8-116">Example</span></span>  
 <span data-ttu-id="94ab8-117">En el ejemplo siguiente se usan las propiedades de navegación `SalesOrderHeader.Address` y `SalesOrderHeader.Contact` para obtener la colección de los objetos `Address` y `Contact` asociados a cada pedido.</span><span class="sxs-lookup"><span data-stu-id="94ab8-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="94ab8-118">El apellido del contacto, la dirección postal, el número de pedidos de venta y el importe total a pagar de cada pedido para la ciudad de Seattle se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="94ab8-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="94ab8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ab8-119">Example</span></span>  
 <span data-ttu-id="94ab8-120">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="94ab8-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="94ab8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ab8-121">See Also</span></span>  
 [<span data-ttu-id="94ab8-122">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="94ab8-122">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
