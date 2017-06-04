---
title: "Usar la capa de sockets seguros | Microsoft Docs"
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
  - "Redes"
  - "SSL"
  - "Capa de sockets seguros"
  - "solicitar datos de Internet, capa de sockets seguros"
  - "enviar datos, capa de sockets seguros"
  - "Recursos de red"
  - "solicitudes de datos, capa de sockets seguros"
  - "recibir datos, capa de sockets seguros"
  - "Internet, capa de sockets seguros"
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Usar la capa de sockets seguros
Las clases de <xref:System.Net> utilizan la capa de sockets seguros \(SSL\) para cifrar la conexión para varios protocolos de red.  
  
 Para las conexiones HTTP, utilice SSL de las clases de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse> de comunicarse con los hosts de web que SSL admiten.  La decisión de utilizar SSL es realizada por la clase de <xref:System.Net.WebRequest> , según el identificador URI proporcionado.  Si el URI comienza con “https: ”, Se utiliza SSL; si el URI comienza con “http: ”, se utiliza una conexión sin cifrar.  
  
 Para utilizar SSL con el Protocolo de transferencia de archivos \(FTP\), establezca la propiedad de <xref:System.Net.FtpWebRequest.EnableSsl> en true antes de llamar a <xref:System.Net.FtpWebRequest.GetResponse>.  De igual forma, utilizar SSL con el Protocolo simple de transferencia de correo \(SMTP\), establezca la propiedad de <xref:System.Net.Mail.SmtpClient.EnableSsl> en true antes de enviar correo electrónico.  
  
 La clase de <xref:System.Net.Security.SslStream> proporciona una abstracción secuencia\- basados en SSL, y proporciona muchas maneras de configurar el control de manos de SSL.  
  
## Ejemplo  
  
### Código  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias al espacio de nombres **System.Net** .  
  
## Vea también  
 [Seguridad en la programación para redes](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Selección y validación de certificados](../../../docs/framework/network-programming/certificate-selection-and-validation.md)