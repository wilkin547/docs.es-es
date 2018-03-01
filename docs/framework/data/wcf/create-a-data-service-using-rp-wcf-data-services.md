---
title: "Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 343fc6043b4cfc7ea02ff33c18aaaf5ced14c11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="353b1-102">Cómo: Crear un servicio de datos utilizando el proveedor de reflexión (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="353b1-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="353b1-103"> le permite definir un modelo de datos que está basado en clases arbitrarias siempre que dichas clases se expongan como objetos que implementan la interfaz <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="353b1-103"> enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="353b1-104">Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="353b1-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="353b1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="353b1-105">Example</span></span>  
 <span data-ttu-id="353b1-106">En el ejemplo siguiente se define un modelo de datos que incluye `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="353b1-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="353b1-107">La clase del contenedor de entidades `OrderItemData` tiene dos métodos públicos que devuelven interfaces <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="353b1-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="353b1-108">Estas interfaces son los conjuntos de entidades de los tipos de entidad `Orders` y `Items`.</span><span class="sxs-lookup"><span data-stu-id="353b1-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="353b1-109">Cada `Order` puede incluir varios `Items`, por lo que el tipo de entidad `Orders` tiene una propiedad de navegación `Items` que devuelve una colección de objetos `Items`.</span><span class="sxs-lookup"><span data-stu-id="353b1-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="353b1-110">La clase del contenedor de entidades `OrderItemData` es el tipo genérico de la clase <xref:System.Data.Services.DataService%601> de la que se deriva el servicio de datos `OrderItems`.</span><span class="sxs-lookup"><span data-stu-id="353b1-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="353b1-111">Dado que este ejemplo muestra un proveedor de datos en memoria y los cambios no se conservan fuera de las instancias de objeto actuales, no hay ninguna ventaja derivada de implementar la interfaz <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="353b1-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="353b1-112">Para obtener un ejemplo que implementa el <xref:System.Data.Services.IUpdatable> de la interfaz, vea [Cómo: crear un servicio de datos mediante un origen de datos SQL de LINQ](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="353b1-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="353b1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="353b1-113">See Also</span></span>  
 [<span data-ttu-id="353b1-114">Creación de un servicio de datos utilizando un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="353b1-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [<span data-ttu-id="353b1-115">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="353b1-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="353b1-116">Creación de un servicio de datos con un origen de datos de ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="353b1-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
