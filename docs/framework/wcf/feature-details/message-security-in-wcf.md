---
title: Seguridad de los mensajes en WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ef96dd25903076fedc59ad1507674dd40dcfcc5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="message-security-in-wcf"></a>Seguridad de los mensajes en WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tiene dos modos principales para proporcionar seguridad (`Transport` y `Message`) y un tercer modo (`TransportWithMessageCredential`) que combina los dos. Este tema trata la seguridad del mensaje y las razones para utilizarla.  
  
## <a name="what-is-message-security"></a>¿Qué es Seguridad de mensaje?  
 Seguridad de mensaje utiliza la especificación de  WS-Security para proteger los mensajes. WS-Securityspecification describe las mejoras en mensajería SOAP para asegurar confidencialidad, integridad y autenticación en el nivel del mensaje SOAP (en lugar del nivel de transporte).  
  
 En resumen, la seguridad de mensaje difiere de la seguridad de transporte encapsulando las credenciales de seguridad y notificaciones con cada mensaje junto con cualquier protección del mensaje (firma o cifrado). La aplicación directa de seguridad al mensaje modificando su contenido permite que el mensaje seguro sea autónomo con respecto a los aspectos de seguridad. Esto habilita algunos escenarios que no son posibles cuando se utiliza la seguridad de transporte.  
  
## <a name="reasons-to-use-message-security"></a>Razones para utilizar Seguridad del mensaje  
 En seguridad de nivel de mensaje, toda la información de seguridad se encapsula en el mensaje. Proteger el mensaje con seguridad de nivel de mensaje en lugar de seguridad de nivel de transporte tiene las siguientes ventajas:  
  
-   Seguridad global. La seguridad de transporte, como Capa de sockets seguros (SSL) solo protege los mensajes cuando la comunicación es de punto a punto. Si el mensaje se dirige a uno o varios intermediarios de SOAP (por ejemplo un enrutador) antes de alcanzar el receptor final, el propio mensaje no está protegido cuando un intermediario lo lee desde la conexión. Además, la información de autenticación del cliente está disponible solamente para el primer intermediario y debe ser transmitida al último receptor en modo fuera de banda, si es necesario. Esto se aplica incluso en el caso de que la ruta completa utilice la seguridad de SSL entre los saltos individuales. Dado que el modo de seguridad funciona directamente con el mensaje y protege el XML en él, la seguridad permanece con el mensaje sin tener en cuenta cuántos intermediarios están implicados antes de alcanzar el receptor final. Esto habilita un verdadero escenario de seguridad integral.  
  
-   Más flexibilidad. Se pueden firmar o cifrar las partes del mensaje, en lugar del mensaje completo. Esto significa que los intermediarios pueden ver las partes del mensaje diseñadas para ellos. Si el remitente necesita que parte de la información en el mensaje sea visible a los intermediarios, pero desea asegurarse que no se manipula, simplemente puede firmarlo sin cifrarlo. Puesto que la firma forma parte del mensaje, el receptor final puede comprobar que ha recibido la información del mensaje intacta. Un escenario podría tener un servicio intermediario de SOAP que dirige el mensaje según lo especificado en el valor de encabezado de Acción. De forma predeterminada, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no cifra el valor de la acción sino que lo firma si se utiliza la seguridad de mensajes. Por consiguiente, todos los intermediarios pueden tener acceso a esta información, pero nadie puede cambiarla.  
  
-   Compatibilidad con varios transportes. Puede enviar mensajes seguros sobre muchos transportes diferentes, como canalizaciones con nombre y TCP, sin tener que confiar en el protocolo para la seguridad. Con seguridad de nivel de transporte, toda la información de seguridad es delimitada a una conexión de transporte determinada única y no está disponible desde el propio contenido del mensaje. La seguridad de mensaje protege el mensaje sin tener en cuenta el transporte que usted utiliza para transmitir el mensaje y el contexto de seguridad se incrusta directamente dentro del mensaje.  
  
-   Compatibilidad con un amplio conjunto de credenciales y notificaciones. La seguridad del mensaje está basada en la especificación WS-Security, que proporciona un marco extensible capaz de transmitir cualquier tipo de notificación dentro del mensaje SOAP. A diferencia de la seguridad de transporte, el conjunto de mecanismos de autenticación, o notificaciones, que puede usar no está limitado por las funciones de transporte. La seguridad de mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye varios tipos de autenticación y transmisión de notificaciones y se puede extender para admitir tipos adicionales según sea necesario. Por esas razones, por ejemplo, no es posible un escenario de credenciales federado sin seguridad de mensaje. Para obtener más información acerca de la federación escenarios WCF admite, consulte [federación y Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="how-message-and-transport-security-compare"></a>Comparación de seguridad de transporte y seguridad de mensajes   
  
### <a name="pros-and-cons-of-transport-level-security"></a>Ventajas y desventajas de Seguridad de nivel de transporte   
 La seguridad de transporte tiene las ventajas siguientes:  
  
-   No requiere que las partes en comunicación entiendan los conceptos de seguridad del nivel de XML. Por ejemplo, esto puede mejorar la interoperabilidad cuando HTTPS se utiliza para proteger la comunicación.  
  
-   Rendimiento generalmente mejorado.  
  
-   Los aceleradores de hardware están disponibles.  
  
-   Es posible la transmisión en secuencias.  
  
 La seguridad de transporte tiene los siguientes inconvenientes:  
  
-   Solo salto a salto.  
  
-   Conjunto de credenciales limitado y no extensible.  
  
-   Dependiente de transporte.  
  
### <a name="disadvantages-of-message-level-security"></a>Desventajas de Seguridad del nivel de mensaje  
 La seguridad de mensaje tiene las siguientes desventajas:  
  
-   Rendimiento  
  
-   No puede utilizar transmisión de mensaje.  
  
-   Requiere implementación de mecanismos de seguridad de nivel XML y la compatibilidad con WS-Security. Esto podría afectar a la interoperabilidad.  
  
## <a name="see-also"></a>Vea también  
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Uso de la seguridad de transporte y las credenciales de mensajes](../../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [Microsoft patrones y prácticas, capítulo 3: seguridad de capa de mensajes y transporte de implementación](http://go.microsoft.com/fwlink/?LinkId=88897)
