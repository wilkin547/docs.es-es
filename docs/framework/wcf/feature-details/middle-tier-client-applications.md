---
title: Aplicaciones cliente de nivel intermedio
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 5019215567f4c9127f2e53fd4cdf0d4a67b84d17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248258"
---
# <a name="middle-tier-client-applications"></a>Aplicaciones cliente de nivel intermedio

En este tema se describen varios problemas específicos de las aplicaciones cliente de nivel intermedio que usan Windows Communication Foundation (WCF).  
  
## <a name="increasing-middle-tier-client-performance"></a>Aumentar el rendimiento del cliente de nivel intermedio  

 En comparación con las tecnologías de comunicaciones anteriores, como los servicios web que usan ASP.NET, la creación de una instancia de cliente de WCF puede ser más compleja debido al amplio conjunto de características de WCF. Por ejemplo, cuando se abre un objeto <xref:System.ServiceModel.ChannelFactory%601>, éste puede establecer una sesión segura con el servicio, un procedimiento que aumenta el tiempo de inicio de la instancia del cliente. Normalmente, estas funciones de características adicionales no afectan a las aplicaciones cliente en gran medida, ya que el cliente de WCF realiza varias llamadas y, a continuación, se cierra.  
  
 Sin embargo, las aplicaciones cliente de nivel intermedio pueden crear muchos objetos de cliente de WCF rápidamente y, como resultado, experimentar un aumento de los requisitos de inicialización. Existen dos enfoques principales para aumentar el rendimiento de aplicaciones de nivel intermedio durante la llamada a los servicios:  
  
- Almacene en caché el objeto de cliente de WCF y vuelva a usarlo para las llamadas subsiguientes siempre que sea posible.  
  
- Cree un <xref:System.ServiceModel.ChannelFactory%601> objeto y, a continuación, use ese objeto para crear nuevos objetos de canal de cliente WCF para cada llamada.  
  
 Problemas que deben tenerse en cuenta cuando se aplican estos enfoques:  
  
- Si el servicio está manteniendo un estado específico del cliente mediante una sesión, no puede volver a usar el cliente de WCF de nivel intermedio con solicitudes de nivel de varios clientes porque el estado del servicio está vinculado al del cliente de nivel intermedio.  
  
- Si el servicio debe realizar la autenticación en cada cliente, debe crear un nuevo cliente para cada solicitud entrante en el nivel intermedio en lugar de volver a usar el cliente de WCF de nivel intermedio (o el objeto de canal de cliente de WCF), ya que las credenciales de cliente del nivel intermedio no se pueden modificar una vez creado el cliente de WCF (o <xref:System.ServiceModel.ChannelFactory%601> ).  
  
- Si bien es cierto que los canales y clientes creados por los canales son seguros para la ejecución de subprocesos, podrían no admitir la escritura de más de un mensaje en la conexión de manera simultánea. Si se envían mensajes grandes, particularmente si se transmite por secuencias, la operación enviada puede bloquearse mientras espera la finalización de otro envío. Esto provoca dos tipos de problemas: la falta de simultaneidad y la posibilidad de interbloqueo si el flujo de control vuelve al servicio que reutiliza el canal (es decir, el cliente compartido llama a un servicio cuya ruta de acceso de código da lugar a una devolución de llamada al cliente compartido). Esto es así independientemente del tipo de cliente de WCF que reutilice.  
  
- Deben controlarse los canales fallidos independientemente de si se comparte o no el canal. Sin embargo, cuando se reutilizan, un canal fallido puede dejar inactiva más de una solicitud o envío pendiente.  
  
 Para ver un ejemplo en el que se muestran los procedimientos recomendados para reutilizar un cliente para varias solicitudes, consulte [enlace de datos en un cliente de ASP.net](../samples/data-binding-in-an-aspnet-client.md).  
  
 Además, puede aumentar el rendimiento de inicio de los clientes que utilizan tipos de datos que se serializan utilizando <xref:System.Xml.Serialization.XmlSerializer> para generar y compilar código de serialización de esos tipos de datos en el tiempo de ejecución, lo que puede dar lugar a un rendimiento de inicio lento. La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones mediante la generación del código de serialización necesario a partir de los ensamblados compilados para la aplicación. Para obtener más información, vea [Cómo: mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vea también

- [Acceso a los servicios mediante un cliente WCF](accessing-services-using-a-client.md)
