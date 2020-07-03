---
title: Usar flujos en la red
description: .NET Framework representa los recursos de red como secuencias. La clase NetworkStream implementa la clase Stream para su uso con recursos de red.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
ms.openlocfilehash: f8d35b43c9b46a77bfd0c78f7d0118093b6fe824
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501981"
---
# <a name="using-streams-on-the-network"></a>Usar flujos en la red
Los recursos de red se representan como secuencias en .NET Framework. Al tratar las secuencias de forma genérica, .NET Framework ofrece lo siguiente:  
  
- Un método común para enviar y recibir datos web. Independientemente del contenido real del archivo (HTML, XML, etc.), la aplicación usará <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> y <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> para enviar y recibir datos.  
  
- Compatibilidad con las secuencias en .NET Framework. Las secuencias se usan por todo .NET Framework, que posee una amplia infraestructura para gestionarlas. Por ejemplo, puede modificar una aplicación que lee datos XML de una <xref:System.IO.FileStream> para que lea los datos de una <xref:System.Net.Sockets.NetworkStream> cambiando únicamente las pocas líneas de código que inicializan la secuencia. Las principales diferencias entre la clase **NetworkStream** y otras secuencias radican en que no se pueden hacer búsquedas en **NetworkStream**, la propiedad <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> siempre devuelve **false** y los métodos <xref:System.Net.Sockets.NetworkStream.Seek%2A> y <xref:System.Net.Sockets.NetworkStream.Position%2A> generan <xref:System.NotSupportedException>.  
  
- Procesamiento de los datos a medida que llegan. Las secuencias proporcionan acceso a los datos a medida que llegan de la red, en lugar de obligar a la aplicación a esperar mientras se descarga un conjunto completo de datos.  
  
 El espacio de nombres <xref:System.Net.Sockets> contiene una clase **NetworkStream** que implementa la clase <xref:System.IO.Stream> específicamente para su uso con recursos de red. Las clases del espacio de nombres <xref:System.Net.Sockets> usan la clase **NetworkStream** para representar las secuencias.  
  
 Para enviar datos a la red mediante la secuencia devuelta, llame a <xref:System.Net.WebRequest.GetRequestStream%2A> en su <xref:System.Net.WebRequest>. **WebRequest** enviará encabezados de solicitud al servidor; después podrá enviar datos al recurso de red mediante una llamada al método <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> o <xref:System.IO.Stream.Write%2A> de la secuencia devuelta. Algunos protocolos, como HTTP, pueden requerir que se establezcan propiedades específicas del protocolo antes de enviar los datos. En el siguiente ejemplo de código se muestra cómo se establecen las propiedades específicas de HTTP para enviar datos. Se presupone que la variable `sendData` contiene los datos que se van a enviar y que la variable `sendLength` es el número de bytes de datos que se van a enviar.  
  
```csharp  
HttpWebRequest request =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 Para recibir datos de la red, llame a <xref:System.Net.WebResponse.GetResponseStream%2A> en su <xref:System.Net.WebResponse>. Después podrá leer los datos del recurso de red mediante una llamada al método <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> o <xref:System.IO.Stream.Read%2A> de la secuencia devuelta.  
  
 Si usa secuencias de recursos de red, tenga en cuenta lo siguiente:  
  
- La propiedad **CanSeek** siempre devuelve **false**, ya que la clase **NetworkStream** no puede cambiar la posición en la secuencia. Los métodos **Seek** y **Position** generan **NotSupportedException**.  
  
- Si usa **WebRequest** y **WebResponse**, las instancias de secuencia creadas mediante la llamada a **GetResponseStream** son de solo lectura, mientras que las instancias de secuencia creadas mediante la llamada a **GetRequestStream** son de solo escritura.  
  
- Use la clase <xref:System.IO.StreamReader> para facilitar la codificación. En el siguiente ejemplo de código se usa un **StreamReader** para leer una secuencia con codificación ASCII de una **WebResponse** (en el ejemplo no se muestra la creación de la solicitud).  
  
- La llamada a **GetResponse** puede bloquearse si los recursos de red no están disponibles. Debe considerar el uso de una solicitud asincrónica con los métodos <xref:System.Net.WebRequest.BeginGetResponse%2A> y <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
- La llamada a **GetRequestStream** puede bloquearse mientras se establece la conexión con el servidor. Debe considerar el uso de una solicitud asincrónica para la secuencia con los métodos <xref:System.Net.WebRequest.BeginGetRequestStream%2A> y <xref:System.Net.WebRequest.EndGetRequestStream%2A>.  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## <a name="see-also"></a>Vea también

- [Cómo: Solicitar datos mediante la clase WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Solicitud de datos](requesting-data.md)
