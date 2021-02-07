---
description: 'Más información acerca de cómo: crear un servicio de datos mediante el proveedor de reflexión (Servicios de datos de WCF)'
title: 'Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 1c4d131b21c69e11dd6d8b574e4c22a6af7c5a25
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766240"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="dafb2-103">Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="dafb2-103">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="dafb2-104">Servicios de datos de WCF permite definir un modelo de datos basado en clases arbitrarias siempre que dichas clases se expongan como objetos que implementan la <xref:System.Linq.IQueryable%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="dafb2-104">WCF Data Services enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="dafb2-105">Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dafb2-105">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dafb2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dafb2-106">Example</span></span>  

 <span data-ttu-id="dafb2-107">En el ejemplo siguiente se define un modelo de datos que incluye `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="dafb2-107">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="dafb2-108">La clase del contenedor de entidades `OrderItemData` tiene dos métodos públicos que devuelven interfaces <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="dafb2-108">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="dafb2-109">Estas interfaces son los conjuntos de entidades de los tipos de entidad `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="dafb2-109">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="dafb2-110">Cada `Order` puede incluir varios `Items`, por lo que el tipo de entidad `Orders` tiene una propiedad de navegación `Items` que devuelve una colección de objetos `Items`.</span><span class="sxs-lookup"><span data-stu-id="dafb2-110">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="dafb2-111">La clase del contenedor de entidades `OrderItemData` es el tipo genérico de la clase <xref:System.Data.Services.DataService%601> de la que se deriva el servicio de datos `OrderItems`.</span><span class="sxs-lookup"><span data-stu-id="dafb2-111">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dafb2-112">Dado que este ejemplo muestra un proveedor de datos en memoria y los cambios no se conservan fuera de las instancias de objeto actuales, no hay ninguna ventaja derivada de implementar la interfaz <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="dafb2-112">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="dafb2-113">Para obtener un ejemplo que implementa la <xref:System.Data.Services.IUpdatable> interfaz, vea [Cómo: crear un servicio de datos mediante un origen de datos de LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="dafb2-113">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="dafb2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dafb2-114">See also</span></span>

- [<span data-ttu-id="dafb2-115">Procedimiento para crear un servicio de datos mediante un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dafb2-115">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="dafb2-116">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="dafb2-116">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="dafb2-117">Procedimiento para crear un servicio de datos con un origen de datos de ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="dafb2-117">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
