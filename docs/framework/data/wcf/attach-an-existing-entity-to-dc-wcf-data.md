---
title: 'Cómo: Asociar una entidad existente a DataServiceContext (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 7c8355ea9e9823e7cab6f43c0f3f901948d1d539
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569378"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Cómo: Asociar una entidad existente a DataServiceContext (Data Services de WCF)
Cuando una entidad ya existe en un servicio de datos, la biblioteca de cliente de WCF Data Services le permite adjuntar un objeto que representa directamente la entidad al <xref:System.Data.Services.Client.DataServiceContext> sin ejecutar primero una consulta. Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un objeto `Customer` existente que contiene cambios que se van a guardar en el servicio de datos. Se adjunta el objeto al contexto y se llama al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> para marcar el objeto adjunto como <xref:System.Data.Services.Client.EntityStates.Modified> antes de llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
