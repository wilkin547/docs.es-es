---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Navegar por relaciones'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
ms.openlocfilehash: 56ae913da3ca06a08b5bacc5ce225597980467a6
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539461"
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="ac8bf-102">Ejemplos de sintaxis de consulta basada en métodos: Navegar por relaciones</span><span class="sxs-lookup"><span data-stu-id="ac8bf-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="ac8bf-103">Las propiedades de navegación de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] son propiedades de acceso directo que se emplean para localizar las entidades situadas en los extremos de una asociación.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="ac8bf-104">Las propiedades de navegación permiten a un usuario navegar de una entidad a otra, o desde una entidad a entidades relacionadas a través de un conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="ac8bf-105">Este tema proporciona ejemplos de sintaxis de consulta basada en métodos de cómo navegar por las relaciones mediante propiedades de navegación en LINQ a consultas de entidades.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="ac8bf-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ac8bf-107">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="ac8bf-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="ac8bf-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8bf-108">Example</span></span>  
 <span data-ttu-id="ac8bf-109">En el ejemplo siguiente de la sintaxis de consulta basada en métodos se usa el método <xref:System.Linq.Queryable.SelectMany%2A> para obtener todos los pedidos de los contactos cuyo apellido es "Zhou".</span><span class="sxs-lookup"><span data-stu-id="ac8bf-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="ac8bf-110">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="ac8bf-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8bf-111">Example</span></span>  
 <span data-ttu-id="ac8bf-112">En el ejemplo siguiente de sintaxis de consulta basada en métodos se utiliza el método <xref:System.Linq.Queryable.Select%2A> para obtener todos los identificadores de contactos y la suma del importe total a pagar de cada contacto cuyo nombre sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="ac8bf-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="ac8bf-113">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="ac8bf-114">El método `Sum` usa la propiedad de navegación `Contact.SalesOrderHeader` para sumar el importe total a pagar de todos los pedidos de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="ac8bf-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8bf-115">Example</span></span>  
 <span data-ttu-id="ac8bf-116">En el ejemplo siguiente de la sintaxis de consulta basada en métodos se obtienen todos los pedidos de los contactos cuyo apellido es "Zhou".</span><span class="sxs-lookup"><span data-stu-id="ac8bf-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="ac8bf-117">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="ac8bf-118">El nombre y los pedidos del contacto se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="ac8bf-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8bf-119">Example</span></span>  
 <span data-ttu-id="ac8bf-120">En el ejemplo siguiente se usan las propiedades de navegación `SalesOrderHeader.Address` y `SalesOrderHeader.Contact` para obtener la colección de los objetos `Address` y `Contact` asociados a cada pedido.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="ac8bf-121">El apellido del contacto, la dirección postal, el número de pedidos de venta y el importe total a pagar de cada pedido para la ciudad de Seattle se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="ac8bf-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8bf-122">Example</span></span>  
 <span data-ttu-id="ac8bf-123">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="ac8bf-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="ac8bf-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac8bf-124">See also</span></span>

- [<span data-ttu-id="ac8bf-125">Las relaciones, las propiedades de navegación y las claves externas</span><span class="sxs-lookup"><span data-stu-id="ac8bf-125">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
- [<span data-ttu-id="ac8bf-126">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ac8bf-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
