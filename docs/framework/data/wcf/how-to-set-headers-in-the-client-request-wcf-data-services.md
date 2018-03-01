---
title: "Cómo: establecer los encabezados en la solicitud de cliente (Data Services de WCF)"
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
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4e923966e3c2a84ad032e546733f00c7672536a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Cómo: establecer los encabezados en la solicitud de cliente (Data Services de WCF)
Cuando use la biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para acceder a un servicio de datos compatible con [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], la biblioteca establece automáticamente los encabezados HTTP necesarios en los mensajes de solicitud enviados al servicio de datos. Sin embargo, la biblioteca cliente no sabe establecer los encabezados de mensaje necesarios en ciertos casos, como cuando el servicio de datos necesita cookies o autenticación basada en notificaciones. Para obtener más información, consulte [proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication). En estos casos, debe establecer manualmente los encabezados de mensaje del mensaje de solicitud antes de enviarlo. En el ejemplo de este tema se muestra cómo controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> para agregar un nuevo encabezado al mensaje de solicitud antes de que se envíe al servicio de datos.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). También puede usar el [servicio de datos de ejemplo Northwind](http://go.microsoft.com/fwlink/?LinkId=187426) que se publica en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sitio Web; estos datos de ejemplo servicio es de solo lectura e intentando guardar cambios devuelve un error. Servicios de los datos de ejemplo en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sitio Web permiten la autenticación anónima.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se registra un controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y, a continuación, se ejecuta una consulta en el servicio de datos.  
  
> [!NOTE]
>  Cuando un servicio de datos necesita que se establezca manualmente el encabezado del mensaje de todas las solicitudes, plantéese registrar el controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> mediante la invalidación del método parcial `OnContextCreated` del contenedor de entidades que represente el servicio de datos, que en este caso es `NorthwindEntities`.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Ejemplo  
 El siguiente método controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y agrega un encabezado de autenticación a la solicitud.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>Vea también  
 [Protección de WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
