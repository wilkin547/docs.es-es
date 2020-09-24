---
title: 'Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 6bab9d9be484cf90cb85df63a1b237b5cc39a5e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152772"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="7be83-102">Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="7be83-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>

<span data-ttu-id="7be83-103">WCF Data Services permite definir un modelo de datos basado en clases arbitrarias siempre que dichas clases se expongan como objetos que implementan la <xref:System.Linq.IQueryable%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="7be83-103">WCF Data Services enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="7be83-104">Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7be83-104">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7be83-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7be83-105">Example</span></span>  

 <span data-ttu-id="7be83-106">En el ejemplo siguiente se define un modelo de datos que incluye `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="7be83-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="7be83-107">La clase del contenedor de entidades `OrderItemData` tiene dos métodos públicos que devuelven interfaces <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="7be83-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="7be83-108">Estas interfaces son los conjuntos de entidades de los tipos de entidad `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="7be83-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="7be83-109">Cada `Order` puede incluir varios `Items`, por lo que el tipo de entidad `Orders` tiene una propiedad de navegación `Items` que devuelve una colección de objetos `Items`.</span><span class="sxs-lookup"><span data-stu-id="7be83-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="7be83-110">La clase del contenedor de entidades `OrderItemData` es el tipo genérico de la clase <xref:System.Data.Services.DataService%601> de la que se deriva el servicio de datos `OrderItems`.</span><span class="sxs-lookup"><span data-stu-id="7be83-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7be83-111">Dado que este ejemplo muestra un proveedor de datos en memoria y los cambios no se conservan fuera de las instancias de objeto actuales, no hay ninguna ventaja derivada de implementar la interfaz <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="7be83-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="7be83-112">Para obtener un ejemplo que implementa la <xref:System.Data.Services.IUpdatable> interfaz, vea [Cómo: crear un servicio de datos mediante un origen de datos de LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="7be83-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="7be83-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7be83-113">See also</span></span>

- [<span data-ttu-id="7be83-114">Procedimiento para crear un servicio de datos mediante un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7be83-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="7be83-115">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="7be83-115">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="7be83-116">Procedimiento para crear un servicio de datos con un origen de datos de ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7be83-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
