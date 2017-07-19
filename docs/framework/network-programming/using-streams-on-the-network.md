---
title: "Usar flujos en la red | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "solicitar datos de Internet, flujos"
  - "Redes"
  - "respuesta a una solicitud de Internet, flujos"
  - "recursos de red, las capacidades de flujo"
  - "recibir datos, capacidades de flujo"
  - "Recursos de red"
  - "enviar datos, capacidades de flujo"
  - "descargar recursos de Internet, flujos"
  - "flujos, capacidades"
  - "Internet, flujos"
  - "secuencias"
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Usar flujos en la red
Representan a recursos de red en .NET Framework como secuencias.  Trata secuencias genéricamente, .NET Framework proporciona las siguientes capacidades:  
  
-   Una manera común de enviar y recibir datos web.  Sea cual sea el contenido real del archivo — HTML, XML, o cualquier otra cosa — la aplicación utilizará <xref:System.IO.Stream.Write%2A?displayProperty=fullName> y <xref:System.IO.Stream.Read%2A?displayProperty=fullName> para enviar y recibir datos.  
  
-   Compatibilidad con secuencias a través de .NET Framework.  Las secuencias se utilizan en .NET Framework, que tiene una infraestructura enriquecida para administrarlas.  Por ejemplo, puede modificar una aplicación que lee datos XML de <xref:System.IO.FileStream> para leer los datos de <xref:System.Net.Sockets.NetworkStream> en su lugar cambiando únicamente las pocas líneas de código que inicialice la secuencia.  Las principales diferencias entre la clase de **NetworkStream** y otras secuencias son que **NetworkStream** no es seekable, la propiedad de <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> siempre devuelven **false**, y los métodos de <xref:System.Net.Sockets.NetworkStream.Seek%2A> y de <xref:System.Net.Sockets.NetworkStream.Position%2A> producen <xref:System.NotSupportedException>.  
  
-   Procesamiento de datos como protege.  Las secuencias proporcionan acceso a los datos como protege de la red, en lugar de forzar la aplicación espere a un conjunto de datos completo que se descargará.  
  
 El espacio de nombres <xref:System.Net.Sockets> contiene una clase de **NetworkStream** que implementa la clase de <xref:System.IO.Stream> específicamente para el uso con los recursos de red.  Las clases del espacio de nombres <xref:System.Net.Sockets> utilizan la clase de **NetworkStream** para representar secuencias.  
  
 Para enviar datos a la red mediante la secuencia devuelta, llame a <xref:System.Net.WebRequest.GetRequestStream%2A> en su <xref:System.Net.WebRequest>.  **WebRequest** enviará encabezados de solicitud al servidor; a continuación puede enviar datos al recurso de red llamando a <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, o un método de <xref:System.IO.Stream.Write%2A> en la secuencia devuelta.  Algunos protocolos, como HTTP, pueden exigirle que establecer propiedades protocolo\- específicas antes de enviar los datos.  El ejemplo de código siguiente muestra cómo establecer las propiedades Http\-específicas para enviar datos.  Se supone que `sendData` variable contiene los datos para enviar y que `sendLength` variable es el número de bytes de datos para enviar.  
  
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
  
 Para recibir datos de red, llame a <xref:System.Net.WebResponse.GetResponseStream%2A> en su <xref:System.Net.WebResponse>.  Puede leer datos de recurso de red llamando a <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, o un método de <xref:System.IO.Stream.Read%2A> en la secuencia devuelta.  
  
 Al utilizar secuencias de recursos de red, tenga presente los puntos siguientes:  
  
-   La propiedad de **CanSeek** siempre devuelve **false** ya que la clase de **NetworkStream** no puede cambiar la posición en la secuencia.  Los métodos de **Seek** y de **Position** producen **NotSupportedException**.  
  
-   Cuando se utiliza **WebRequest** y **WebResponse**, las instancias de la secuencia creadas llamando a **GetResponseStream** son de solo lectura y las instancias de la secuencia creadas llamando a **GetRequestStream** son de solo escritura.  
  
-   Utilice la clase de <xref:System.IO.StreamReader> para crear codificar más fácil.  El siguiente ejemplo de código utiliza **StreamReader** para leer una secuencia ASCII\- codificada de **WebResponse** \(el ejemplo no muestra crear la solicitud\).  
  
-   La llamada a **GetResponse** puede bloquear si los recursos de red no están disponibles.  Se debería utilizar una solicitud asincrónica con los métodos de <xref:System.Net.WebRequest.BeginGetResponse%2A> y de <xref:System.Net.WebRequest.EndGetResponse%2A> .  
  
-   La llamada a **GetRequestStream** puede bloquearse mientras la conexión al servidor se crea.  Se debería utilizar una solicitud asincrónica para la secuencia con los métodos de <xref:System.Net.WebRequest.BeginGetRequestStream%2A> y de <xref:System.Net.WebRequest.EndGetRequestStream%2A> .  
  
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
  
## Vea también  
 [Cómo solicitar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)