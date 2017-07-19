---
title: "Realizar solicitudes asincr&#243;nicas | Microsoft Docs"
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
  - "Internet, acceso asincrónico"
  - "Redes"
  - "solicitudes asincrónicas, recursos de Internet"
  - "Recursos de red"
  - "clase WebRequest, acceso asincrónico"
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Realizar solicitudes asincr&#243;nicas
Las clases de <xref:System.Net> utilizan el modelo de programación asincrónica estándar de.NET framework para el acceso asincrónico a los recursos de internet.  Los métodos de <xref:System.Net.WebRequest.BeginGetResponse%2A> y de <xref:System.Net.WebRequest.EndGetResponse%2A> de la clase de <xref:System.Net.WebRequest> comienzan y completan las solicitudes asincrónicas para un recurso de internet.  
  
> [!NOTE]
>  Mediante llamadas sincrónicas en métodos de devolución de llamada asincrónicos puede provocar pérdidas graves de rendimiento.  Las solicitudes de internet realizadas con **WebRequest** y sus descendientes deben utilizar <xref:System.IO.Stream.BeginRead%2A?displayProperty=fullName> para leer la secuencia devuelta por el método de <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName> .  
  
 El ejemplo siguiente muestra cómo utilizar llamadas asincrónicas a la clase de **WebRequest** .  El ejemplo es un programa de consola que toma un identificador URI de la línea de comandos, solicita el recurso en el URI, y después datos imprime en la consola cuando se recibe de internet.  
  
 El programa define dos clases para su propio uso, la clase de **RequestState** , que pasa datos a través de llamadas asincrónicas, y la clase de **ClientGetAsync** , que implementa la solicitud asincrónica a un recurso de internet.  
  
 La clase de **RequestState** mantiene el estado de la solicitud a través de llamadas a los métodos asincrónicos que mantienen la solicitud.  Contiene **WebRequest** y las instancias de <xref:System.IO.Stream> que contienen la solicitud actual el recurso y la secuencia recibidos en respuesta, un búfer que contiene los datos recibidos actualmente del recurso de internet, y <xref:System.Text.StringBuilder> que contiene la respuesta completa.  **RequestState**se pasa como el parámetro *de estado* cuando el método de <xref:System.AsyncCallback> se registra con **WebRequest.BeginGetResponse**.  
  
 La clase de **ClientGetAsync** implementa una solicitud asincrónica a un recurso de internet y escribir la respuesta resultante en la consola.  Contiene los métodos y propiedades descritos en la siguiente lista.  
  
-   La propiedad de `allDone` contiene una instancia de la clase de <xref:System.Threading.ManualResetEvent> que señala la finalización de la solicitud.  
  
-   El método de `Main()` lee la línea de comandos e inicia la solicitud para el recurso de internet especificado.  Crea **WebRequest**`wreq` y **RequestState**`rs`, llama a **BeginGetResponse** para iniciar procesa la solicitud, y después llamar al método de `allDone.WaitOne()`de modo que no deja la aplicación hasta que se complete la devolución de llamada.  Después de que la respuesta se lea del recurso de internet, `Main()` la escribe en la consola y los extremos de la aplicación.  
  
-   El método de `showusage()` escribe una línea de comandos de ejemplo en la consola.  Llama `Main()` cuando no se proporciona ningún URI en la línea de comandos.  
  
-   El método de `RespCallBack()` implementa el método de devolución de llamada asincrónico para la solicitud de internet.  Crea la instancia de **WebResponse** que contiene la respuesta del recurso de internet, obtiene la secuencia de respuesta, y después inicia leer los datos de la secuencia de forma asincrónica.  
  
-   El método de `ReadCallBack()` implementa el método de devolución de llamada asincrónico para leer la secuencia de respuesta.  Transfiere los datos recibidos del recurso de internet en la propiedad de **ResponseData** de la instancia de **RequestState** , inicia otra lectura asincrónica de respuesta transmitir hasta que se devuelve no más de datos.  Una vez que se ha leído todos los datos, `ReadCallBack()` cierre la respuesta transmitir y llama al método de `allDone.Set()` para indicar que toda la respuesta está presente en **ResponseData**.  
  
    > [!NOTE]
    >  Es fundamental que se cierran todas las secuencias de red.  Si no cierra cada secuencia de solicitud y respuesta, se ejecutará la aplicación de conexiones al servidor y no podrá procesar solicitudes adicionales.  
  
```csharp  
using System;  
using System.Net;  
using System.Threading;  
using System.Text;  
using System.IO;  
  
// The RequestState class passes data across async calls.  
public class RequestState  
{  
   const int BufferSize = 1024;  
   public StringBuilder RequestData;  
   public byte[] BufferRead;  
   public WebRequest Request;  
   public Stream ResponseStream;  
   // Create Decoder for appropriate enconding type.  
   public Decoder StreamDecode = Encoding.UTF8.GetDecoder();  
  
   public RequestState()  
   {  
      BufferRead = new byte[BufferSize];  
      RequestData = new StringBuilder(String.Empty);  
      Request = null;  
      ResponseStream = null;  
   }       
}  
  
// ClientGetAsync issues the async request.  
class ClientGetAsync   
{  
   public static ManualResetEvent allDone = new ManualResetEvent(false);  
   const int BUFFER_SIZE = 1024;  
  
   public static void Main(string[] args)   
   {  
      if (args.Length < 1)   
      {  
         showusage();  
         return;  
      }  
  
      // Get the URI from the command line.  
      Uri httpSite = new Uri(args[0]);  
  
      // Create the request object.  
      WebRequest wreq = WebRequest.Create(httpSite);  
  
      // Create the state object.  
      RequestState rs = new RequestState();  
  
      // Put the request into the state object so it can be passed around.  
      rs.Request = wreq;  
  
      // Issue the async request.  
      IAsyncResult r = (IAsyncResult) wreq.BeginGetResponse(  
         new AsyncCallback(RespCallback), rs);  
  
      // Wait until the ManualResetEvent is set so that the application   
      // does not exit until after the callback is called.  
      allDone.WaitOne();  
  
      Console.WriteLine(rs.RequestData.ToString());  
   }  
  
   public static void showusage() {  
      Console.WriteLine("Attempts to GET a URL");  
      Console.WriteLine("\r\nUsage:");  
      Console.WriteLine("   ClientGetAsync URL");  
      Console.WriteLine("   Example:");  
      Console.WriteLine("      ClientGetAsync http://www.contoso.com/");  
   }  
  
   private static void RespCallback(IAsyncResult ar)  
   {  
      // Get the RequestState object from the async result.  
      RequestState rs = (RequestState) ar.AsyncState;  
  
      // Get the WebRequest from RequestState.  
      WebRequest req = rs.Request;  
  
      // Call EndGetResponse, which produces the WebResponse object  
      //  that came from the request issued above.  
      WebResponse resp = req.EndGetResponse(ar);           
  
      //  Start reading data from the response stream.  
      Stream ResponseStream = resp.GetResponseStream();  
  
      // Store the response stream in RequestState to read   
      // the stream asynchronously.  
      rs.ResponseStream = ResponseStream;  
  
      //  Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead  
      IAsyncResult iarRead = ResponseStream.BeginRead(rs.BufferRead, 0,   
         BUFFER_SIZE, new AsyncCallback(ReadCallBack), rs);   
   }  
  
   private static void ReadCallBack(IAsyncResult asyncResult)  
   {  
      // Get the RequestState object from AsyncResult.  
      RequestState rs = (RequestState)asyncResult.AsyncState;  
  
      // Retrieve the ResponseStream that was set in RespCallback.   
      Stream responseStream = rs.ResponseStream;  
  
      // Read rs.BufferRead to verify that it contains data.   
      int read = responseStream.EndRead( asyncResult );  
      if (read > 0)  
      {  
         // Prepare a Char array buffer for converting to Unicode.  
         Char[] charBuffer = new Char[BUFFER_SIZE];  
  
         // Convert byte stream to Char array and then to String.  
         // len contains the number of characters converted to Unicode.  
      int len =   
         rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0);  
  
         String str = new String(charBuffer, 0, len);  
  
         // Append the recently read data to the RequestData stringbuilder  
         // object contained in RequestState.  
         rs.RequestData.Append(  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read));           
  
         // Continue reading data until   
         // responseStream.EndRead returns –1.  
         IAsyncResult ar = responseStream.BeginRead(   
            rs.BufferRead, 0, BUFFER_SIZE,   
            new AsyncCallback(ReadCallBack), rs);  
      }  
      else  
      {  
         if(rs.RequestData.Length>0)  
         {  
            //  Display data to the console.  
            string strContent;                    
            strContent = rs.RequestData.ToString();  
         }  
         // Close down the response stream.  
         responseStream.Close();           
         // Set the ManualResetEvent so the main thread can exit.  
         allDone.Set();                             
      }  
      return;  
   }      
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Threading  
Imports System.Text  
Imports System.IO  
  
' The RequestState class passes data across async calls.  
Public Class RequestState  
  
      Public RequestData As New StringBuilder("")  
      Public BufferRead(1024) As Byte  
      Public Request As HttpWebRequest  
      Public ResponseStream As Stream  
      ' Create Decoder for appropriate encoding type.  
      Public StreamDecode As Decoder = Encoding.UTF8.GetDecoder()  
  
      Public Sub New  
         Request = Nothing  
         ResponseStream = Nothing  
      End Sub  
End Class  
  
' ClientGetAsync issues the async request.  
Class ClientGetAsync  
   Shared allDone As New ManualResetEvent(False)  
      Const BUFFER_SIZE As Integer = 1024  
  
    Shared Sub Main()  
        Dim Args As String() = Environment.GetCommandLineArgs()  
  
        If Args.Length < 2 Then  
            ShowUsage()  
            Return  
        End If  
  
      ' Get the URI from the command line.  
        Dim HttpSite As Uri = New Uri(Args(1))  
  
      ' Create the request object.  
        Dim wreq As HttpWebRequest = _  
           CType(WebRequest.Create(HttpSite), HttpWebRequest)  
  
      ' Create the state object.  
      Dim rs As RequestState = New RequestState()  
  
      ' Put the request into the state so it can be passed around.  
      rs.Request = wreq  
  
      ' Issue the async request.  
        Dim r As IAsyncResult = _  
           CType(wreq.BeginGetResponse( _  
           New AsyncCallback(AddressOf RespCallback), rs), IAsyncResult)  
  
      ' Wait until the ManualResetEvent is set so that the application  
      ' does not exit until after the callback is called.  
        allDone.WaitOne()  
    End Sub  
  
    Shared Sub ShowUsage()  
        Console.WriteLine("Attempts to GET a URI")  
        Console.WriteLine()  
        Console.WriteLine("Usage:")  
        Console.WriteLine("ClientGetAsync URI")  
        Console.WriteLine("Examples:")  
        Console.WriteLine("ClientGetAsync http://www.contoso.com/")  
    End Sub  
  
    Shared Sub RespCallback(ar As IAsyncResult)  
       ' Get the RequestState object from the async result.  
       Dim rs As RequestState = CType(ar.AsyncState, RequestState)  
  
       ' Get the HttpWebRequest from RequestState.  
       Dim req As HttpWebRequest= rs.Request  
  
       ' Call EndGetResponse, which returns the HttpWebResponse object  
       ' that came from the request issued above.  
       Dim resp As HttpWebResponse = _  
           CType(req.EndGetResponse(ar), HttpWebResponse)  
  
       ' Start reading data from the respons stream.  
       Dim ResponseStream As Stream = resp.GetResponseStream()  
  
       ' Store the reponse stream in RequestState to read  
       ' the stream asynchronously.  
       rs.ResponseStream = ResponseStream  
  
       ' Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead.  
       Dim iarRead As IAsyncResult = _  
          ResponseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
          New AsyncCallback(AddressOf ReadCallBack), rs)  
    End Sub  
  
   Shared Sub ReadCallBack(asyncResult As IAsyncResult)  
      ' Get the RequestState object from the AsyncResult.  
      Dim rs As RequestState = CType(asyncResult.AsyncState, RequestState)  
  
      ' Retrieve the ResponseStream that was set in RespCallback.  
      Dim responseStream As Stream = rs.ResponseStream  
  
      ' Read rs.BufferRead to verify that it contains data.  
      Dim read As Integer = responseStream.EndRead( asyncResult )  
      If read > 0 Then  
         ' Prepare a Char array buffer for converting to Unicode.  
         Dim charBuffer(1024) As Char  
  
         ' Convert byte stream to Char array and then String.  
         ' len contains the number of characters converted to Unicode.  
         Dim len As Integer = _  
           rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0)  
         Dim str As String = new String(charBuffer, 0, len)      
  
         ' Append the recently read data to the RequestData stringbuilder   
         ' object contained in RequestState.  
         rs.RequestData.Append( _  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read))  
  
         ' Continue reading data until responseStream.EndRead  
         ' returns –1.  
         Dim ar As IAsyncResult = _  
            responseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
            New AsyncCallback(AddressOf ReadCallBack), rs)  
      Else  
          If rs.RequestData.Length > 1 Then  
            ' Display data to the console.  
            Dim strContent As String  
            strContent = rs.RequestData.ToString()  
            Console.WriteLine(strContent)  
         End If  
  
         ' Close down the response stream.  
         responseStream.Close()  
  
         ' Set the ManualResetEvent so the main thread can exit.  
         allDone.Set()  
      End If  
  
      Return  
   End Sub  
End Class  
```  
  
## Vea también  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)