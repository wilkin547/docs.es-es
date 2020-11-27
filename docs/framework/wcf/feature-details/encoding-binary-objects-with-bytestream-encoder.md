---
title: Codificar objetos binarios con codificador de ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276742"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Codificar objetos binarios con codificador de ByteStream

El envío y la recepción de datos binarios sin formato con Windows Communication Foundation (WCF) se configura mediante <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .  
  
## <a name="byte-stream-message-encoder-architecture"></a>Arquitectura de codificador de mensajes de secuencia de bytes  

 El codificador de mensajes binario utilizado por WCF no tiene ninguna utilidad para procesar, validar o identificar los datos binarios subyacentes en el mensaje. El paquete de datos se codifica en XML, se envía, se recibe y se descodifica. El codificador procesa los datos tras haberse enviado al transporte y antes de que el mensaje se envíe a la cola de mensajes. Funcionalmente, el codificador binario ajusta los datos del mensaje en elementos `<binary>` para enviar y quita los elementos una vez recibido el mensaje.  
  
## <a name="using-the-byte-stream-message-encoder"></a>Usar el codificador de mensajes de secuencia de bytes  

 En el siguiente ejemplo, se muestra un contrato de servicios que implementa el codificador de mensajes de secuencia de bytes.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 El siguiente ejemplo muestra el servicio que se invoca.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 En caso de utilizar un servicio que implementa una infraestructura del mensaje (como un enrutador), el mensaje se procesa sin inspeccionar, validar o interactuar de cualquier manera con el mensaje, tal y como se muestra en el siguiente ejemplo.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>Escenarios  

 El codificador de secuencias de bytes es útil en los siguientes escenarios.  
  
- Transferencia de una imagen JPEG entre equipos mediante WCF. En este escenario, la imagen llegará a través del transporte desde un origen externo y los datos enviados serán los bytes sin formato que formen la imagen. Un servicio recibirá los datos binarios y mostrará la imagen.  
  
- Al leer información de una cola de mensajes y procesarla. El mensaje se leerá de un administrador de colas de mensajes y se pasará al canal de cola de mensajes para tratarlo. El canal de cola de mensajes actuará como administrador de cola en la pila de canales de WCF.  
  
 En el caso de enviar un mensaje a través de un canal de cola de mensajes, el remitente no tiene el control sobre los bytes que se reciben del administrador de la cola. Si el proceso de recepción no tiene la capacidad de leer los bytes sin formato, el mensaje se recibirá con formato incorrecto y no se procesará; se supone que el proceso de recepción tendrá la capacidad de traducir los bytes recibidos de nuevo a un formato utilizable.
