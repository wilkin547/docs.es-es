---
title: "Autenticación de NTLM y Kerberos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 36e88b163ab857180a02278828dba7dcec457736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ntlm-and-kerberos-authentication"></a>Autenticación de NTLM y Kerberos
La autenticación NTLM predeterminada y la autenticación Kerberos usan las credenciales de usuario de Microsoft Windows NT asociadas a la aplicación que realiza la llamada para intentar la autenticación con el servidor. Cuando se usa la autenticación NTLM no predeterminada, la aplicación establece el tipo de autenticación en NTLM y usa un objeto <xref:System.Net.NetworkCredential> para pasar el nombre de usuario, la contraseña y el dominio al host, como se muestra en el ejemplo siguiente.  
  
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
  
 Las aplicaciones que necesitan conectarse a los servicios de Internet mediante las credenciales del usuario de la aplicación pueden hacerlo con las credenciales predeterminadas del usuario, como se muestra en el ejemplo siguiente.  
  
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
  
 El módulo de autenticación de negociación determina si el servidor remoto está usando la autenticación NTLM o Kerberos, y envía la respuesta adecuada.  
  
> [!NOTE]
>  La autenticación NTLM no funciona a través de un servidor proxy.  
  
## <a name="see-also"></a>Vea también  
 [Básica y la autenticación implícita](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [Internet Authentication](../../../docs/framework/network-programming/internet-authentication.md) (Autenticación de Internet)
