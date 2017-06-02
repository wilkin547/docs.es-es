---
title: "Autenticaci&#243;n b&#225;sica e impl&#237;cita | Microsoft Docs"
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
  - "autenticación [.NET Framework], clases"
  - "Autenticación básica"
  - "autenticación [.NET Framework], básica"
  - "autenticación de cliente, básica"
  - "autenticación de usuario, básica"
  - "autenticación [.NET Framework], resumen"
  - "recibir datos, autenticación"
  - "autenticación de cliente, implícita"
  - "Internet, autenticación"
  - "autenticación implícita"
  - "enviar datos, autenticación"
  - "recursos de red, autenticación"
  - "autenticación de usuario, implícita"
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Autenticaci&#243;n b&#225;sica e impl&#237;cita
La implementación de <xref:System.Net> de básica y la autenticación implícita cumple RFC2617 – autenticación HTTP: básico y autenticación implícita \(disponible en el sitio web de World Wide Web Consortium en www.w3.org\).  
  
 Para utilizar autenticación básica e implícita, una aplicación debe proporcionar un nombre de usuario y una contraseña en la propiedad de <xref:System.Net.WebRequest.Credentials%2A> del objeto de <xref:System.Net.WebRequest> que utiliza para solicitar datos de internet, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  Los datos enviados con autenticación básica e implícita no se cifra, por lo que los datos se pueden ver mediante un adversario.  Además, las credenciales de autenticación básica \(nombre de usuario y contraseña\) se envían en desactive y pueden ser interceptadas.  
  
## Vea también  
 [Autenticación de NTLM y Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Autenticación de Internet](../../../docs/framework/network-programming/internet-authentication.md)