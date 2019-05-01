---
title: Elección del transporte
ms.date: 03/30/2017
helpviewer_keywords:
- choosing transports [WCF]
ms.assetid: b169462b-f7b6-4cf4-9fca-d306909ee8bf
ms.openlocfilehash: 4d5fe4c92f0d456942219bc3f7014f09a005aa5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048301"
---
# <a name="choosing-a-transport"></a>Elección del transporte
En este tema se describe los criterios para elegir entre los tres transportes principales que se incluyen en Windows Communication Foundation (WCF): HTTP, TCP y canalizaciones con nombre. WCF también incluye un message Queue Server (también conocido como MSMQ) de transporte, pero este documento no cubre message Queue Server.  
  
 El modelo de programación WCF separa las operaciones de punto de conexión (tal y como se expresa en un contrato de servicio) desde el mecanismo de transporte que conecta dos puntos de conexión. Esto le proporciona la flexibilidad para decidir cómo exponer sus servicios a la red.  
  
 En WCF, especifica cómo transferir datos a través de una red entre los puntos de conexión mediante el uso de un *enlace*, que se compone de una secuencia de *elementos de enlace*. Un elemento de enlace del transporte, que forma parte del enlace, representa un transporte. Un enlace incluye los elementos de enlace de protocolo opcionales, como seguridad, un elemento de enlace de codificador de mensaje necesario y un elemento de enlace de transporte necesario. Un transporte envía o recibe el formulario serializado de un mensaje a otra aplicación o desde otra aplicación.  
  
 Si se debe conectar a un cliente existente o servidor, puede que no tenga elección a la hora de utilizar un transporte determinado. Sin embargo, los servicios de WCF pueden hacerse accesibles a través de varios extremos, cada uno con un transporte diferente. Cuando un transporte único no cubre el público previsto para su servicio, considere exponer el servicio sobre varios extremos. De este modo, las aplicaciones cliente pueden utilizar el punto de conexión que más les convenga.  
  
 Después de elegir un transporte, debe seleccionar un enlace que lo utilice. Puede elegir un enlace proporcionado por el sistema (consulte [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)), o bien puede crear su propio enlace personalizado (vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)). Además, puede crear sus propios enlaces. Para obtener más información, consulte [crear enlaces](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="advantages-of-each-transport"></a>Ventajas de cada transporte  
 En esta sección se describen las razones principales para elegir cualquiera de los tres transportes principales y se muestra un gráfico de decisión detallado para elegir entre ellos.  
  
### <a name="when-to-use-http-transport"></a>Cuándo utilizar el transporte HTTP  
 HTTP es un protocolo de solicitud/respuesta entre clientes y servidores. La aplicación más común consiste en clientes de explorador web que se comunican con un servidor web. El cliente envía una solicitud a un servidor, que escucha los mensajes de la solicitud de cliente. Cuando el servidor reciba una solicitud, devuelve una respuesta, que contiene el estado de la solicitud. Si es correcto, se devuelven datos opcionales como una página web, un mensaje de error u otra información. Para obtener más información sobre el protocolo HTTP, consulte [HTTP - protocolo de transferencia de hipertexto](https://go.microsoft.com/fwlink/?LinkId=94858).  
  
 El protocolo HTTP no está basado en una conexión. Una vez enviada la respuesta, no se mantiene ningún estado. Para administrar transacciones de varias páginas, la aplicación debe conservar cualquier estado necesario.  
  
 En WCF, el transporte HTTP enlace se optimiza para la interoperabilidad con sistemas heredados no WCF. Si todas las partes en comunicación usa WCF, los enlaces basados en canalizaciones con nombre o basados en TCP son más rápidos. Para obtener más información, vea <xref:System.ServiceModel.NetTcpBinding> y <xref:System.ServiceModel.NetNamedPipeBinding>.  
  
### <a name="when-to-use-the-tcp-transport"></a>Cuando utilizar el transporte TCP.  
 TCP es un servicio de entrega basado en conexión, orientado a secuencias con detección de errores de principio a fin y corrección. *Basado en conexión* significa que se establece una sesión de comunicación entre los hosts antes de intercambiar datos. Un host es un dispositivo en una red TCP/IP identificada por una dirección IP lógica.  
  
 TCP proporciona entrega de datos de confianza y facilidad de uso. En concreto, TCP notifica al remitente la entrega del paquete, garantiza que los paquetes se entregan en el mismo orden en el que se envían, retransmite los paquetes perdidos y se asegura de que no se dupliquen los paquetes de datos. Tenga en cuenta que esta entrega de confianza se aplica entre dos nodos de TCP/IP y no es lo mismo que *WS-ReliableMessaging*, que se aplica entre puntos de conexión, independientemente de cuántos nodos intermedios pueden incluir.  
  
 El transporte TCP de WCF está optimizado para el escenario donde usa ambos extremos de la comunicación de WCF. Este enlace es el enlace de WCF más rápido para escenarios que implican comunicación entre equipos diferentes. Los intercambios de mensajes utilizan <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> para la transferencia de mensajes optimizada. TCP proporciona comunicación dúplex y, de este modo, se puede utilizar para implementar los contratos dúplex, incluso cuando el cliente está detrás de la traducción de direcciones de red (NAT).  
  
### <a name="when-to-use-the-named-pipe-transport"></a>Cuándo utilizar el transporte de la canalización con nombre  
 Una canalización con nombre es un objeto en el kernel del sistema operativo Windows, como una sección de memoria compartida que pueden utilizar los procesos para la comunicación. Una canalización con nombre tiene un nombre y se puede utilizar para la comunicación unidireccional o dúplex entre los procesos en un solo equipo.  
  
 Cuando se requiere comunicación entre distintas aplicaciones de WCF en un único equipo y desea evitar cualquier comunicación desde otro equipo, a continuación, use el transporte de canalizaciones con nombre. Una restricción adicional es que los procesos que se ejecutan desde el Escritorio remoto de Windows pueden estar limitados a la misma sesión de Escritorio remoto de Windows, a no ser que tengan privilegios elevados.  
  
> [!WARNING]
>  Al utilizar el transporte de canalización con nombre con una reserva de direcciones URL de carácter comodín débil en varios sitios hospedados en IIS, puede producirse el error siguiente: Se produjo un error en el servicio de activación 'NetPipeActivator' del protocolo 'net.pipe' al intentar realizar escuchas para el sitio '2', por lo tanto el protocolo está deshabilitado temporalmente para el sitio. Vea el mensaje de excepción para obtener más detalles. Dirección URL: WeakWildcard:net.pipe:/\<nombre del equipo > / estado: ConflictingRegistration excepción:  Nombre del proceso: Id. de proceso SMSvcHost: 1076\  
  
## <a name="decision-points-for-choosing-a-transport"></a>Puntos de decisión para elegir un transporte  
 La tabla siguiente describe los puntos de decisión comunes utilizados para elegir un transporte. Debería considerar los atributos adicionales y transportes que se aplican a su aplicación. Identifique los atributos que son importantes para su aplicación, identifique los transportes que se asocian favorablemente con cada uno de sus atributos y, a continuación, seleccione los transportes que funcionen mejor con su configuración de atributos.  
  
|Atributo|Descripción|Transportes favorables|  
|---------------|-----------------|------------------------|  
|Diagnóstico|Los diagnósticos le permiten detectar automáticamente los problemas de conectividad de transporte. Todos los transportes admiten la capacidad de devolver la información del error que describe la conectividad. Sin embargo, WCF incluye herramientas de diagnóstico para investigar los problemas de red.|Ninguna|  
|Hospedaje|Todos los extremos WCF se deben hospedar dentro de una aplicación. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] y las versiones anteriores solo admiten hospedar aplicaciones que usan el transporte HTTP. En [!INCLUDE[wv](../../../../includes/wv-md.md)], soporte técnico se agrega para hospedar todos los transportes WCF, incluido TCP y canalizaciones con nombre. Para obtener más información, consulte [hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md) y [hospedaje en Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).|HTTP|  
|Inspección|La inspección es la capacidad de extraer y procesar la información de los mensajes durante la transmisión. El protocolo HTTP separa el enrutamiento e información de control de los datos, de modo que facilita la creación de herramientas que inspeccionan y analizan los mensajes. Los transportes que son fáciles de inspeccionar también pueden requerir menos potencia de procesamiento en dispositivos de red. El nivel de seguridad utilizado afecta a la posibilidad de inspeccionar los mensajes.|HTTP|  
|Latency|La latencia es el período de tiempo mínimo exigido para completar un intercambio de mensajes. Todas las operaciones de red tienen más o menos latencia, según la elección de transporte. El uso de dúplex o comunicación unidireccional con un transporte cuyo patrón de intercambio de mensajes nativo es la respuesta de la solicitud, como HTTP, puede producir la latencia adicional debido a la correlación forzada de mensajes. En esta situación, considere utilizar un transporte cuyo patrón de intercambio de mensajes nativo sea dúplex, como TCP.|TCP, con nombre<br /><br /> Canalización (|).|  
|Reach|El alcance de un transporte refleja cómo es de capaz el transporte al conectar con otros sistemas. El transporte de canalización con nombre tiene un alcance muy pequeño; solo puede conectar a los servicios que se ejecutan en el mismo equipo. Los transportes HTTP y TCP tienen un alcance excelente y pueden penetrar algunas configuraciones de firewall y NAT. Para obtener más información, consulte [trabajar con NAT y Firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md).|HTTP, TCP|  
|Seguridad|Seguridad es la capacidad de proteger los mensajes durante la transferencia proporcionando confidencialidad, integridad o autenticación. La confidencialidad protege un mensaje para que no pueda ser examinado, la integridad protege un mensaje contra su modificación y la autenticación proporciona garantías sobre el remitente o receptor del mensaje.<br /><br /> WCF admite la seguridad de transferencia en el nivel de mensaje y el nivel de transporte. La seguridad de mensaje se crea con un transporte si el transporte admite un modo de transferencia almacenado en búfer. La compatibilidad de la seguridad de transporte varía, dependiendo del transporte escogido. El HTTP, TCP y transportes de canalización con nombre tienen paridad razonable en su compatibilidad de seguridad de transporte.|Todas|  
|Rendimiento|El rendimiento mide la cantidad de datos que se pueden transmitir y se pueden procesar en un período de tiempo especificado. Como la latencia, el transporte escogido puede afectar al rendimiento de las operaciones de servicio. Maximizar el rendimiento de un transporte requiere minimizar tanto la sobrecarga de transmisión de contenido como el tiempo de espera empleado para que se completen los intercambios de mensajes. Tanto los transportes de canalización con nombre y TCP agregan sobrecarga pequeña al cuerpo del mensaje y admiten una forma dúplex nativa que reduce la espera en las respuestas de los mensaje.|TCP, canalización con nombre|  
|Tooling|Las herramientas representan soporte de aplicaciones de terceros para un protocolo para el desarrollo, diagnóstico, hospedaje y otras actividades. Desarrollar herramientas y software para trabajar con el protocolo HTTP implica una inversión particularmente grande.|HTTP|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)
