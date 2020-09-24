---
title: 'Cómo: Asociar una entidad existente a DataServiceContext (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 69ca64f4ab3470c1a4f58c582b31c06aed9cadd5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166136"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Cómo: Asociar una entidad existente a DataServiceContext (Data Services de WCF)

Cuando una entidad ya existe en un servicio de datos, la biblioteca de cliente de WCF Data Services le permite adjuntar un objeto que representa la entidad directamente a <xref:System.Data.Services.Client.DataServiceContext> sin ejecutar primero una consulta. Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo crear un objeto `Customer` existente que contiene cambios que se van a guardar en el servicio de datos. Se adjunta el objeto al contexto y se llama al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> para marcar el objeto adjunto como <xref:System.Data.Services.Client.EntityStates.Modified> antes de llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Consulte también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
