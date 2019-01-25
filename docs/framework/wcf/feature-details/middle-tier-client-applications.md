---
title: Aplicaciones cliente de nivel intermedio
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 457a215274c4804ac38958d8f840e8f4100a7be0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718902"
---
# <a name="middle-tier-client-applications"></a>Aplicaciones cliente de nivel intermedio
En este tema se describe varios problemas específicos de las aplicaciones de cliente de nivel intermedio que usan Windows Communication Foundation (WCF).  
  
## <a name="increasing-middle-tier-client-performance"></a>Aumentar el rendimiento del cliente de nivel intermedio  
 En comparación con las tecnologías de comunicación anteriores, como servicios Web mediante [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], la creación de una instancia de cliente WCF puede ser más compleja debido al conjunto completo de características de WCF. Por ejemplo, cuando se abre un objeto <xref:System.ServiceModel.ChannelFactory%601>, éste puede establecer una sesión segura con el servicio, un procedimiento que aumenta el tiempo de inicio de la instancia del cliente. Normalmente, estas características adicionales no afectan a las aplicaciones cliente en gran medida puesto que el cliente de WCF hace varias llamadas y, a continuación, se cierra.  
  
 Las aplicaciones cliente de nivel intermedio, sin embargo, pueden crear rápidamente muchos objetos de cliente WCF y, como resultado, experimentar los requisitos de inicialización de una mayor. Existen dos enfoques principales para aumentar el rendimiento de aplicaciones de nivel intermedio durante la llamada a los servicios:  
  
-   Almacenar en caché el objeto de cliente WCF y reutilizarlo para llamadas subsiguientes, siempre que sea posible.  
  
-   Crear un <xref:System.ServiceModel.ChannelFactory%601> de objetos y, a continuación, usar ese objeto para crear objetos de canal para cada llamada de cliente WCF nuevo.  
  
 Problemas que deben tenerse en cuenta cuando se aplican estos enfoques:  
  
-   Si el servicio mantiene un estado específico de cliente mediante el uso de una sesión, no se puede reutilizar al cliente de WCF de nivel intermedio con solicitudes de cliente de varios niveles porque el estado del servicio está asociado a la del cliente de nivel intermedio.  
  
-   Si el servicio debe realizar la autenticación en una base por cliente, debe crear un nuevo cliente para cada solicitud entrante en el nivel intermedio en lugar de reutilizar el cliente de WCF de nivel intermedio (o el objeto de canal de cliente WCF) porque las credenciales del cliente de nivel intermedio no se puede modificar después de que el cliente WCF (o <xref:System.ServiceModel.ChannelFactory%601>) se ha creado.  
  
-   Si bien es cierto que los canales y clientes creados por los canales son seguros para la ejecución de subprocesos, podrían no admitir la escritura de más de un mensaje en la conexión de manera simultánea. Si se envían mensajes grandes, particularmente si se transmite por secuencias, la operación enviada puede bloquearse mientras espera la finalización de otro envío. Esto provoca dos tipos de problemas: la falta de simultaneidad y la posibilidad de interbloqueo si el flujo de control vuelve al servicio que reutiliza el canal (es decir, el cliente compartido llama a un servicio cuya ruta de acceso de código da lugar a una devolución de llamada al cliente compartido). Esto es cierto independientemente del tipo de cliente WCF, volver a usar.  
  
-   Deben controlarse los canales fallidos independientemente de si se comparte o no el canal. Sin embargo, cuando se reutilizan, un canal fallido puede dejar inactiva más de una solicitud o envío pendiente.  
  
 Para obtener un ejemplo que muestra los procedimientos recomendados para reutilizar un cliente para varias solicitudes, consulte [enlace de datos en un cliente de ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Además, puede aumentar el rendimiento de inicio de los clientes que utilizan tipos de datos que se serializan utilizando <xref:System.Xml.Serialization.XmlSerializer> para generar y compilar código de serialización de esos tipos de datos en el tiempo de ejecución, lo que puede dar lugar a un rendimiento de inicio lento. El [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones generando el código de serialización necesarios desde los ensamblados compilados para la aplicación. Para obtener más información, vea [Cómo: Mejorar el inicio de tiempo de las aplicaciones cliente WCF mediante XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vea también
- [Acceso a los servicios mediante un cliente WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
