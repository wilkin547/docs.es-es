---
title: Transferencia de mensajes por secuencias
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72a47a51-e5e7-4b76-b24a-299d51e0ae5a
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ff9cedb589b9df79e17efcedc783938cc3c6647e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="streaming-message-transfer"></a>Transferencia de mensajes por secuencias
Los transportes de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admiten dos modos para transferir los mensajes:  
  
-   Las transferencias almacenadas en búfer contienen el mensaje completo en un búfer de memoria hasta que la transferencia haya finalizado. Un mensaje almacenado en búfer debe entregarse por completo antes de que un receptor pueda leerlo.  
  
-   Las transferencias por secuencias exponen el mensaje como una secuencia. El receptor inicia a procesar el mensaje antes de que se haya entregado por completo.  
  
-   Las transferencias por secuencias pueden mejorar la escalabilidad de un servicio eliminando el requisito de grandes búferes de memoria. La mejora de la escalabilidad mediante el cambio del modo de transferencia depende del tamaño de los mensajes que se estén transfiriendo. Los tamaños de mensaje grandes favorecen el uso de transferencias por secuencias.  
  
 De forma predeterminada, los transportes HTTP, TCP/IP, y de canalización con nombre usan transferencias almacenadas en búfer. En este documento se describe cómo intercambiar estos transportes desde un modo de transferencia almacenado en búfer hasta otro de transferencia por secuencias y las consecuencias de ello.  
  
## <a name="enabling-streamed-transfers"></a>Habilitación de transferencias por secuencias  
 La selección entre los modos de transferencia mediante búfer y mediante secuencias se realiza en el elemento de enlace del transporte. El elemento de enlace tiene una propiedad <xref:System.ServiceModel.TransferMode> que puede establecerse en `Buffered`, `Streamed`, `StreamedRequest`o `StreamedResponse`. Establecer el modo de transferencia en `Streamed` habilita la comunicación de transmisión por secuencias en ambas direcciones. Establecer el modo de transferencia en `StreamedRequest` o `StreamedResponse` habilita la comunicación de la transmisión por secuencias solo en la dirección indicada.  
  
 Los enlaces <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.NetTcpBinding>, y <xref:System.ServiceModel.NetNamedPipeBinding> exponen la propiedad <xref:System.ServiceModel.TransferMode>. Para otros transportes, debe crear un enlace personalizado para establecer el modo de transferencia.  
  
 La decisión de utilizar transferencias almacenadas en búfer o transmitidas es una decisión local del extremo. En los transportes HTTP, el modo de transferencia no se propaga a través de una conexión o a los servidores y otros intermediarios. Establecer el modo de transferencia no se refleja en la descripción de la interfaz de servicio. Después de generar una clase de cliente para un servicio, debe modificar el archivo de configuración de los servicios pensados para ser utilizados con transferencias por secuencias para establecer el modo. En los transportes con canalizaciones con nombre y TCP, el modo de transferencia se propaga como una aserción de directiva.  
  
 Para obtener ejemplos de código, vea [Cómo: habilitar la transmisión por secuencias](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md).  
  
## <a name="enabling-asynchronous-streaming"></a>Habilitar la transmisión de datos asincrónica  
 Para habilitar el streaming asincrónico, agregue el comportamiento de extremo <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> al host de servicio y establezca la propiedad <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> en `true`.  
  
 Esta versión de WCF también agrega la capacidad de auténtica transmisión de datos asincrónica en el lado de envío. Esto mejora la escalabilidad del servicio en escenarios donde transmite por secuencias mensajes para varios clientes, algunos de los cuales son lentos en la lectura; posiblemente debido a la congestión de red o que no leen en absoluto. En estos escenarios WCF ya bloquea los subprocesos individuales en el servicio por cliente. Esto garantiza que el servicio pueda procesar muchos más clientes, mejorando así la escalabilidad del servicio.  
  
## <a name="restrictions-on-streamed-transfers"></a>Restricciones en transferencias por secuencias  
 El uso del modo de transferencia por secuencias hace que el tiempo de ejecución exija restricciones adicionales.  
  
 Las operaciones que se producen en un transporte por secuencias pueden tener un contrato con, como mucho, un parámetro de entrada o de salida. Ese parámetro corresponde al cuerpo completo del mensaje y ha de ser un <xref:System.ServiceModel.Channels.Message>, un tipo derivado de <xref:System.IO.Stream>, o una implementación <xref:System.Xml.Serialization.IXmlSerializable>. Tener un valor devuelto para una operación equivale a tener un parámetro de salida.  
  
 Algunas características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como la mensajería de confianza, las transacciones y la seguridad del nivel del mensaje SOAP, confían en almacenar en búfer los mensajes para las transmisiones. El uso de estas características puede reducir o eliminar las ventajas de rendimiento ganadas mediante la transmisión por secuencias. Para proteger un transporte por secuencias, utilice la seguridad de nivel de transporte únicamente o utilice la seguridad de nivel de transporte más la seguridad de mensaje de solo autenticación.  
  
 Los encabezados SOAP siempre están almacenados en búfer, incluso cuando el modo de transferencia es por secuencias. Los encabezados de un mensaje no deben superar el tamaño de la cuota de transporte `MaxBufferSize`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Esta configuración, vea [las cuotas de transporte](../../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
## <a name="differences-between-buffered-and-streamed-transfers"></a>Diferencias entre las transferencias almacenadas en búfer y las transferencias por secuencias  
 Si se cambia el modo de transferencia de almacenado en búfer a por secuencias, también se cambia la forma del canal nativo de transportes de canalización con nombre y TCP. Para transferencias almacenadas en búfer, la forma del canal nativo es <xref:System.ServiceModel.Channels.IDuplexSessionChannel>. Para las transferencias por secuencias, los canales nativos son <xref:System.ServiceModel.Channels.IRequestChannel> y <xref:System.ServiceModel.Channels.IReplyChannel>. Al cambiar el modo de transferencia en una aplicación existente que utiliza estos transportes directamente (es decir, no a través de un contrato de servicios), requiere el cambio de la forma del canal esperada para los generadores de canales y agentes de escucha.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: habilitar la transmisión por secuencias](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
