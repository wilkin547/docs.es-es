---
title: Procedimiento Agregar, modificar y eliminar entidades (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: a00f8933-b232-4445-95ba-adc634f055d8
ms.openlocfilehash: 66f115bf3bf51b4b5612240c4e34eaf9e08bec0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59518089"
---
# <a name="how-to-add-modify-and-delete-entities-wcf-data-services"></a>Procedimiento Agregar, modificar y eliminar entidades (WCF Data Services)
Con el [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bibliotecas de cliente, se puede crear, actualizar y eliminar datos de entidad en un servicio de datos realizando las acciones equivalentes en los objetos de la <xref:System.Data.Services.Client.DataServiceContext>. Para obtener más información, consulte [actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean cuando se completa la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se crea una nueva instancia de objeto y, a continuación, se llama al método <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext> para crear el elemento en el contexto. Se envía un mensaje POST de HTTP al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addproduct)]
 [!code-vb[Astoria Northwind Client#AddProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addproduct)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se recupera y modifica un objeto existente y, a continuación, se llama al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> en <xref:System.Data.Services.Client.DataServiceContext> para marcar el elemento en el contexto cuando se actualice. Cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> se envía un mensaje HTTP MERGE al servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#modifycustomer)]
 [!code-vb[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#modifycustomer)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se llama al método <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> en <xref:System.Data.Services.Client.DataServiceContext> para marcar el elemento en el contexto cuando se elimine. Cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> se envía un mensaje HTTP DELETE al servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#deleteproduct)]
 [!code-vb[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#deleteproduct)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una instancia de objeto nueva y, a continuación, se llama al método <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext> para crear el elemento en el contexto junto con el vínculo al pedido relacionado. Se envía un mensaje POST de HTTP al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Cómo: Asociar una entidad existente a DataServiceContext](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md)
- [Cómo: Definir relaciones de entidades](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md)
- [Procesamiento por lotes de operaciones](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)
