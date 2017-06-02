---
title: "Autenticaci&#243;n de NTLM y Kerberos | Microsoft Docs"
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
  - "autenticación [.NET Framework], NTLM"
  - "autenticación [.NET Framework], Kerberos"
  - "autenticación de usuario, Kerberos"
  - "autenticación de usuario, NTLM"
  - "Autenticación de Kerberos"
  - "recibir datos, autenticación"
  - "autenticación NTLM"
  - "Internet, autenticación"
  - "autenticación de cliente, Kerberos"
  - "enviar datos, autenticación"
  - "recursos de red, autenticación"
  - "clases [.NET Framework], autenticación"
  - "autenticación del cliente, NTLM"
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Autenticaci&#243;n de NTLM y Kerberos
La autenticación NTLM predeterminada y la autenticación Kerberos utilizan las credenciales de usuario de Microsoft Windows NT asociadas a la aplicación de llamada para intentar la autenticación con el servidor.  Al utilizar la autenticación NTLM de no predeterminado, la aplicación establece el tipo de autenticación a NTLM y utiliza un objeto de <xref:System.Net.NetworkCredential> para pasar el nombre de usuario, la contraseña, y el dominio al host, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 Las aplicaciones que necesitan conectarse a los servicios Internet utilizando las credenciales de usuario de la aplicación pueden hacerlo con credenciales predeterminadas del usuario, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 El módulo de autenticación de negociación determina si el servidor remoto utiliza NTLM o la autenticación Kerberos, y envía la respuesta adecuada.  
  
> [!NOTE]
>  La autenticación NTLM no funciona a través de un servidor proxy.  
  
## Vea también  
 [Autenticación básica e implícita](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Autenticación de Internet](../../../docs/framework/network-programming/internet-authentication.md)