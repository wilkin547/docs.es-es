---
title: Aplicaciones cliente de nivel intermedio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73641fcbc881e57465f722d3a0f647938a5e12e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="middle-tier-client-applications"></a>Aplicaciones cliente de nivel intermedio
En este tema se exponen varios problemas específicos de las aplicaciones cliente de nivel intermedio que utilizan [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="increasing-middle-tier-client-performance"></a>Aumentar el rendimiento del cliente de nivel intermedio  
 En comparación con tecnologías de comunicación anteriores, como los servicios web que utilizan [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], la creación de una instancia de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede ser más compleja debido al conjunto enriquecido de características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Por ejemplo, cuando se abre un objeto <xref:System.ServiceModel.ChannelFactory%601>, éste puede establecer una sesión segura con el servicio, un procedimiento que aumenta el tiempo de inicio de la instancia del cliente. Normalmente, estas características adicionales no tienen gran repercusión en las aplicaciones cliente ya que el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] realiza varias llamadas, y, a continuación, se cierra.  
  
 No obstante, las aplicaciones cliente de nivel intermedio pueden crear rápidamente muchos objetos cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y, como resultado, experimentar un incremento de los requisitos de inicialización. Existen dos enfoques principales para aumentar el rendimiento de aplicaciones de nivel intermedio durante la llamada a los servicios:  
  
-   Almacenar en memoria caché el objeto cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y reutilizarlo para llamadas subsiguientes, siempre que sea posible.  
  
-   Crear un objeto <xref:System.ServiceModel.ChannelFactory%601> y, a continuación, utilizarlo para crear nuevos objetos de canal cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para cada llamada.  
  
 Problemas que deben tenerse en cuenta cuando se aplican estos enfoques:  
  
-   Si el servicio mantiene un estado específico de cliente mediante una sesión, no puede reutilizarse el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de nivel intermedio con múltiples solicitudes de cliente intermedio porque el estado del servicio está vinculado al del este tipo de cliente.  
  
-   Si el servicio realiza la autenticación basándose en cada cliente, cree un nuevo cliente para cada solicitud entrante en el nivel intermedio, en lugar de volver a utilizar el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de nivel intermedio (u objeto de canal de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]), ya que no pueden modificarse las credenciales del cliente de nivel intermedio una vez creado el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (o <xref:System.ServiceModel.ChannelFactory%601>).  
  
-   Si bien es cierto que los canales y clientes creados por los canales son seguros para la ejecución de subprocesos, podrían no admitir la escritura de más de un mensaje en la conexión de manera simultánea. Si se envían mensajes grandes, particularmente si se transmite por secuencias, la operación enviada puede bloquearse mientras espera la finalización de otro envío. Esto provoca dos tipos de problemas: la falta de simultaneidad y la posibilidad de interbloqueo si el flujo de control vuelve al servicio que reutiliza el canal (es decir, el cliente compartido llama a un servicio cuya ruta de acceso de código da lugar a una devolución de llamada al cliente compartido). Esto es así independientemente del tipo de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que reutiliza.  
  
-   Deben controlarse los canales fallidos independientemente de si se comparte o no el canal. Sin embargo, cuando se reutilizan, un canal fallido puede dejar inactiva más de una solicitud o envío pendiente.  
  
 Para obtener un ejemplo que muestra los procedimientos recomendados para volver a usar un cliente para varias solicitudes, consulte [enlace de datos en un cliente ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Además, puede aumentar el rendimiento de inicio de los clientes que utilizan tipos de datos que se serializan utilizando <xref:System.Xml.Serialization.XmlSerializer> para generar y compilar código de serialización de esos tipos de datos en el tiempo de ejecución, lo que puede dar lugar a un rendimiento de inicio lento. El [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones al generar el código de serialización necesarios desde los ensamblados compilados para la aplicación. Para obtener más información, consulte [Cómo: mejorar el inicio del tiempo de aplicaciones cliente de WCF mediante XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vea también  
 [Acceso a los servicios mediante un cliente WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
