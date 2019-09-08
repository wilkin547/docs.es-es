---
title: Procedimiento Establecer encabezados en la solicitud de cliente (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 42987b1a855589954d45dae13b70ffc056c35f3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790475"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Procedimiento Establecer encabezados en la solicitud de cliente (WCF Data Services)
Cuando use la biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para acceder a un servicio de datos compatible con [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], la biblioteca establece automáticamente los encabezados HTTP necesarios en los mensajes de solicitud enviados al servicio de datos. Sin embargo, la biblioteca cliente no sabe establecer los encabezados de mensaje necesarios en ciertos casos, como cuando el servicio de datos necesita cookies o autenticación basada en notificaciones. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md#clientAuthentication). En estos casos, debe establecer manualmente los encabezados de mensaje del mensaje de solicitud antes de enviarlo. En el ejemplo de este tema se muestra cómo controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> para agregar un nuevo encabezado al mensaje de solicitud antes de que se envíe al servicio de datos.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md). También puede usar el [servicio de datos de ejemplo Northwind](https://go.microsoft.com/fwlink/?LinkId=187426) que se publica en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] el sitio web de; este servicio de datos de ejemplo es de solo lectura y si se intentan guardar los cambios, se devuelve un error. Los servicios de datos de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ejemplo del sitio web permiten la autenticación anónima.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se registra un controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y, a continuación, se ejecuta una consulta en el servicio de datos.  
  
> [!NOTE]
> Cuando un servicio de datos necesita que se establezca manualmente el encabezado del mensaje de todas las solicitudes, plantéese registrar el controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> mediante la invalidación del método parcial `OnContextCreated` del contenedor de entidades que represente el servicio de datos, que en este caso es `NorthwindEntities`.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Ejemplo  
 El siguiente método controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y agrega un encabezado de autenticación a la solicitud.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>Vea también

- [Protección de WCF Data Services](securing-wcf-data-services.md)
- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
