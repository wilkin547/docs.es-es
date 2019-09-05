---
title: 'Ejemplos de sintaxis de expresiones de consulta: Navegar por relaciones'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
ms.openlocfilehash: 38a8ddfe4366fefccd0a874a2ad7a20424ef8fac
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249466"
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="4c736-102">Ejemplos de sintaxis de expresiones de consulta: Navegar por relaciones</span><span class="sxs-lookup"><span data-stu-id="4c736-102">Query Expression Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="4c736-103">Las propiedades de navegación de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] son propiedades de acceso directo que se emplean para localizar las entidades situadas en los extremos de una asociación.</span><span class="sxs-lookup"><span data-stu-id="4c736-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="4c736-104">Las propiedades de navegación permiten a un usuario navegar de una entidad a otra, o desde una entidad a entidades relacionadas a través de un conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="4c736-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="4c736-105">En este tema se proporcionan ejemplos de sintaxis de expresiones de consulta sobre cómo navegar por las relaciones a través de las propiedades de navegación en LINQ to Entities consultas.</span><span class="sxs-lookup"><span data-stu-id="4c736-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="4c736-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4c736-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4c736-107">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4c736-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="4c736-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c736-108">Example</span></span>  
 <span data-ttu-id="4c736-109">En el ejemplo siguiente se usa el método <xref:System.Linq.Queryable.Select%2A> para obtener todos los identificadores de contactos y la suma del importe total a pagar de cada contacto cuyo nombre sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="4c736-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="4c736-110">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="4c736-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="4c736-111">El método `Sum` usa la propiedad de navegación `Contact.SalesOrderHeader` para sumar el importe total a pagar de todos los pedidos de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="4c736-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="4c736-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c736-112">Example</span></span>  
 <span data-ttu-id="4c736-113">El ejemplo siguiente obtiene todos los pedidos de los contactos cuyo apellido sea "Zhou".</span><span class="sxs-lookup"><span data-stu-id="4c736-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="4c736-114">La propiedad de navegación `Contact.SalesOrderHeader` se utiliza para obtener la colección de objetos `SalesOrderHeader` para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="4c736-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="4c736-115">El nombre y los pedidos del contacto se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="4c736-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="4c736-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c736-116">Example</span></span>  
 <span data-ttu-id="4c736-117">En el ejemplo siguiente se usan las propiedades de navegación `SalesOrderHeader.Address` y `SalesOrderHeader.Contact` para obtener la colección de los objetos `Address` y `Contact` asociados a cada pedido.</span><span class="sxs-lookup"><span data-stu-id="4c736-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="4c736-118">El apellido del contacto, la dirección postal, el número de pedidos de venta y el importe total a pagar de cada pedido para la ciudad de Seattle se devuelven en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="4c736-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="4c736-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c736-119">Example</span></span>  
 <span data-ttu-id="4c736-120">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="4c736-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="4c736-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c736-121">See also</span></span>

- [<span data-ttu-id="4c736-122">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4c736-122">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
