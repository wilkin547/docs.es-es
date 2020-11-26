---
title: Procedimiento para habilitar el streaming
description: Obtenga información sobre cómo habilitar mensajes transmitidos en WCF en lugar de las transferencias almacenadas en búfer predeterminadas, que se deben recibir por completo antes de que se procesen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6ca2cf4b-c7a1-49d8-a79b-843a90556ba4
ms.openlocfilehash: 7f77c406e1cfd4def116a1abe24aa92be74c6abe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237747"
---
# <a name="how-to-enable-streaming"></a>Procedimiento para habilitar el streaming

Windows Communication Foundation (WCF) puede enviar mensajes mediante transferencias almacenadas en búfer o por secuencias. En el modo de transferencia almacenado en búfer (predeterminado), se debe entregar completamente un mensaje antes de que un receptor pueda leerlo. En modo de transferencia de transmisión por secuencias, el receptor puede empezar a procesar el mensaje antes de se entregue completamente. El modo de transmisión por secuencias es útil cuando la información que se pasa es larga y puede procesarse en serie. El modo de transmisión por secuencias también es útil cuando el mensaje es demasiado grande para que se almacene en búfer completamente.  
  
 Para habilitar la transmisión por secuencias, defina apropiadamente `OperationContract` y habilite la transmisión por secuencias en el nivel de transporte.  
  
### <a name="to-stream-data"></a>Transmisión de datos por secuencias  
  
1. Para transmitir datos por secuencias, `OperationContract` del servicio debe satisfacer dos requisitos:  
  
    1. El parámetro que contiene los datos que se van a transmitir debe ser el único parámetro del método. Por ejemplo, si el mensaje de entrada es el que se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de entrada. De igual forma, si el mensaje de salida se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de salida o un valor devuelto.  
  
    2. Al menos uno de los tipos del parámetro y el valor devuelto debería ser <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>o <xref:System.Xml.Serialization.IXmlSerializable>.  
  
     A continuación se muestra un ejemplo de los datos.  
  
     [!code-csharp[c_HowTo_EnableStreaming#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#1)]
     [!code-vb[c_HowTo_EnableStreaming#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#1)]  
  
     La operación `GetStream` recibe algunos datos de entrada en búfer como `string`, que también se almacena en búfer y devuelve `Stream`, que se transmite por secuencias. A la inversa, `UploadStream` admite una `Stream` (transmitida por secuencias) y devuelve un `bool` (almacenado en búfer). `EchoStream` toma y devuelve `Stream` y es un ejemplo de una operación cuyos mensajes de entrada y salida se transmiten por secuencias. Finalmente, `GetReversedStream` no toma ninguna entrada y devuelve un `Stream` (transmitido por secuencia).  
  
2. La transmisión por secuencias debe habilitarse en el enlace. Defina una propiedad `TransferMode`, que puede adoptar uno de los siguientes valores:  
  
    1. `Buffered`,  
  
    2. `Streamed`, que habilita la comunicación mediante transmisión por secuencias en ambas direcciones.  
  
    3. `StreamedRequest`, que solo habilita la solicitud de transmisión.  
  
    4. `StreamedResponse`, que solo habilita la transmisión por secuencias de la respuesta.  
  
     `BasicHttpBinding` expone la propiedad `TransferMode` en el enlace, tal y como hace, `NetTcpBinding` y `NetNamedPipeBinding`. La propiedad `TransferMode` se puede establecer también en el elemento de enlace del transporte y utilizarse en un enlace personalizado.  
  
     Los siguientes ejemplos muestran cómo establecer `TransferMode` mediante código y cambiando el archivo de configuración. Ambos ejemplos también establecen la propiedad `maxReceivedMessageSize` en 64 MB, que coloca un límite en el tamaño máximo permitido de mensajes que se reciben. El `maxReceivedMessageSize` predeterminado es de 64 KB, que normalmente es demasiado pequeño para los escenarios de transmisión por secuencias. Establezca este valor de cuota que depende, según corresponda, del tamaño máximo de mensajes que su aplicación espera recibir. También tenga en cuenta que `maxBufferSize` controla el tamaño máximo que se almacena en búfer y lo establece de manera apropiada.  
  
    1. El siguiente fragmento de código de configuración del ejemplo muestra cómo establecer la propiedad `TransferMode` en la transmisión por secuencias en `basicHttpBinding` y un enlace HTTP personalizado.  
  
         [!code-xml[c_HowTo_EnableStreaming#103](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/common/app.config#103)]
  
    2. El siguiente fragmento de código muestra cómo establecer la propiedad `TransferMode` para la transmisión por secuencias en `basicHttpBinding` y un enlace HTTP personalizado.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#2)]
         [!code-vb[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#2)]  
  
    3. El siguiente fragmento de código muestra cómo establecer la propiedad `TransferMode` para la transmisión por secuencias en un enlace HTTP personalizado.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#3)]
         [!code-vb[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#3)]  
  
3. Las operaciones `GetStream`, `UploadStream` y `EchoStream` tratan con el envío de datos directamente desde un archivo o guardando los datos recibidos directamente en un archivo. El siguiente código se aplica a `GetStream`.  
  
     [!code-csharp[c_HowTo_EnableStreaming#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#4)]
     [!code-vb[c_HowTo_EnableStreaming#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#4)]  
  
### <a name="writing-a-custom-stream"></a>Escritura de una secuencia personalizada  
  
1. Para hacer un procesamiento especial en cada fragmento de un flujo de datos mientras se envía o recibe, derive una clase de flujo personalizada de <xref:System.IO.Stream>. Como un ejemplo de una secuencia personalizada, el siguiente código contiene un método `GetReversedStream` y una clase `ReverseStream`.  
  
     `GetReversedStream` crea y devuelve una nueva instancia de `ReverseStream`. El procesamiento real se produce cuando el sistema lee desde el objeto `ReverseStream`. El método `ReverseStream.Read` lee un fragmento de bytes del archivo subyacente, los invierte y después devuelve los bytes invertidos. Este método no invierte el contenido del archivo completo, sino un fragmento de bytes cada vez. Este ejemplo muestra cómo puede realizar el procesamiento de la secuencia cuando el contenido se lee o escribe desde la secuencia.  
  
     [!code-csharp[c_HowTo_EnableStreaming#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#2)]
     [!code-vb[c_HowTo_EnableStreaming#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Datos de gran tamaño y secuencias](large-data-and-streaming.md)
- [Stream](../samples/stream.md)
