---
title: Filtrar Adjuntar una entidad existente a DataServiceContext (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 6fa8e9d66fa89eb058aafd1e74164097b7f5c3a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157864"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Filtrar Adjuntar una entidad existente a DataServiceContext (WCF Data Services)
Cuando una entidad ya existe en un servicio de datos, el [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente le permite adjuntar un objeto que representa la entidad directamente en el <xref:System.Data.Services.Client.DataServiceContext> sin ejecutar primero una consulta. Para obtener más información, consulte [actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean cuando se completa la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un objeto `Customer` existente que contiene cambios que se van a guardar en el servicio de datos. Se adjunta el objeto al contexto y se llama al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> para marcar el objeto adjunto como <xref:System.Data.Services.Client.EntityStates.Modified> antes de llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Data Services de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
