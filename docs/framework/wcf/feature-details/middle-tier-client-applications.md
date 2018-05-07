---
title: Aplicaciones cliente de nivel intermedio
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 4cca832266b2eb2ab7b1b4eb1a5fe937525db97d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="middle-tier-client-applications"></a>Aplicaciones cliente de nivel intermedio
En este tema se describe varios problemas específicos de las aplicaciones de cliente de nivel intermedio que utilizan Windows Communication Foundation (WCF).  
  
## <a name="increasing-middle-tier-client-performance"></a>Aumentar el rendimiento del cliente de nivel intermedio  
 En comparación con tecnologías de comunicación anteriores, como los servicios Web que utilizan [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], la creación de una instancia de cliente WCF puede ser más compleja debido al conjunto enriquecido de características de WCF. Por ejemplo, cuando se abre un objeto <xref:System.ServiceModel.ChannelFactory%601>, éste puede establecer una sesión segura con el servicio, un procedimiento que aumenta el tiempo de inicio de la instancia del cliente. Normalmente, estas características adicionales no afectan a las aplicaciones cliente en gran medida ya que el cliente de WCF realiza varias llamadas y, a continuación, se cierra.  
  
 Las aplicaciones de cliente de nivel intermedio, sin embargo, pueden crear rápidamente muchos objetos de cliente WCF y, como resultado, experimentar requisitos de inicialización mayor. Existen dos enfoques principales para aumentar el rendimiento de aplicaciones de nivel intermedio durante la llamada a los servicios:  
  
-   Almacenar en caché el objeto de cliente WCF y reutilizarlo para llamadas posteriores siempre que sea posible.  
  
-   Crear un <xref:System.ServiceModel.ChannelFactory%601> de objeto y, a continuación, usar ese objeto para crear objetos de canal para cada llamada de cliente WCF nueva.  
  
 Problemas que deben tenerse en cuenta cuando se aplican estos enfoques:  
  
-   Si el servicio mantiene un estado específico de cliente mediante una sesión, no se puede reutilizar al cliente WCF de nivel intermedio con las solicitudes de cliente de varios niveles porque el estado del servicio está asociado a la el cliente de nivel intermedio.  
  
-   Si el servicio debe realizar la autenticación en una base por cliente, debe crear un nuevo cliente para cada solicitud entrante en el nivel intermedio en lugar de volver a usar el cliente de WCF de nivel intermedio (u objeto de canal de cliente WCF) porque las credenciales del cliente de nivel intermedio no se puede modificar después de que el cliente WCF (o <xref:System.ServiceModel.ChannelFactory%601>) se ha creado.  
  
-   Si bien es cierto que los canales y clientes creados por los canales son seguros para la ejecución de subprocesos, podrían no admitir la escritura de más de un mensaje en la conexión de manera simultánea. Si se envían mensajes grandes, particularmente si se transmite por secuencias, la operación enviada puede bloquearse mientras espera la finalización de otro envío. Esto provoca dos tipos de problemas: la falta de simultaneidad y la posibilidad de interbloqueo si el flujo de control vuelve al servicio que reutiliza el canal (es decir, el cliente compartido llama a un servicio cuya ruta de acceso de código da lugar a una devolución de llamada al cliente compartido). Esto es cierto independientemente del tipo de cliente WCF que volver a usar.  
  
-   Deben controlarse los canales fallidos independientemente de si se comparte o no el canal. Sin embargo, cuando se reutilizan, un canal fallido puede dejar inactiva más de una solicitud o envío pendiente.  
  
 Para obtener un ejemplo que muestra los procedimientos recomendados para volver a usar un cliente para varias solicitudes, consulte [enlace de datos en un cliente ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Además, puede aumentar el rendimiento de inicio de los clientes que utilizan tipos de datos que se serializan utilizando <xref:System.Xml.Serialization.XmlSerializer> para generar y compilar código de serialización de esos tipos de datos en el tiempo de ejecución, lo que puede dar lugar a un rendimiento de inicio lento. El [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones al generar el código de serialización necesarios desde los ensamblados compilados para la aplicación. Para obtener más información, consulte [Cómo: mejorar el inicio del tiempo de aplicaciones cliente de WCF mediante XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vea también  
 [Acceso a los servicios mediante un cliente WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
