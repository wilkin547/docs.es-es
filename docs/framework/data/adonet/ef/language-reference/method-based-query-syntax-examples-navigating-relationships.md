---
title: "Ejemplos de sintaxis de consultas basadas en métodos: navegar por relaciones"
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
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 42ea8030a9d832117a10feb6b937d05807033c91
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="df901-102">Ejemplos de sintaxis de consultas basadas en métodos: navegar por relaciones</span><span class="sxs-lookup"><span data-stu-id="df901-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="df901-103">Las propiedades de navegación de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] son propiedades de acceso directo que se emplean para localizar las entidades situadas en los extremos de una asociación.</span><span class="sxs-lookup"><span data-stu-id="df901-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="df901-104">Las propiedades de navegación permiten a un usuario navegar de una entidad a otra, o desde una entidad a entidades relacionadas a través de un conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="df901-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="df901-105">En este tema se ofrecen ejemplos de la sintaxis de consulta basada métodos para navegar por las relaciones a través de propiedades de navegación de las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df901-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="df901-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="df901-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="df901-107">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="df901-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="df901-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df901-108">Example</span></span>  
 <span data-ttu-id="df901-109">En el ejemplo siguiente de la sintaxis de consulta basada en métodos se usa el método <xref:System.Linq.Queryable.SelectMany%2A> para obtener todos los pedidos de los contactos cuyo apellido es "Zhou".</span><span class="sxs-lookup"><span data-stu-id="df901-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="df901-110">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="df901-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="df901-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df901-111">Example</span></span>  
 <span data-ttu-id="df901-112">En el ejemplo siguiente de sintaxis de consulta basada en métodos se utiliza el método <xref:System.Linq.Queryable.Select%2A> para obtener todos los identificadores de contactos y la suma del importe total a pagar de cada contacto cuyo nombre sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="df901-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="df901-113">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="df901-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="df901-114">El método `Sum` usa la propiedad de navegación `Contact.SalesOrderHeader` para sumar el importe total a pagar de todos los pedidos de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="df901-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="df901-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df901-115">Example</span></span>  
 <span data-ttu-id="df901-116">En el ejemplo siguiente de la sintaxis de consulta basada en métodos se obtienen todos los pedidos de los contactos cuyo apellido es "Zhou".</span><span class="sxs-lookup"><span data-stu-id="df901-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="df901-117">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="df901-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="df901-118">El nombre y los pedidos del contacto se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="df901-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="df901-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df901-119">Example</span></span>  
 <span data-ttu-id="df901-120">En el ejemplo siguiente se usan las propiedades de navegación `SalesOrderHeader.Address` y `SalesOrderHeader.Contact` para obtener la colección de los objetos `Address` y `Contact` asociados a cada pedido.</span><span class="sxs-lookup"><span data-stu-id="df901-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="df901-121">El apellido del contacto, la dirección postal, el número de pedidos de venta y el importe total a pagar de cada pedido para la ciudad de Seattle se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="df901-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="df901-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df901-122">Example</span></span>  
 <span data-ttu-id="df901-123">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="df901-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="df901-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="df901-124">See Also</span></span>  
 [<span data-ttu-id="df901-125">Propiedades de navegación</span><span class="sxs-lookup"><span data-stu-id="df901-125">Navigation Properties</span></span>](http://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="df901-126">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="df901-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
