---
title: Autenticación de NTLM y Kerberos
description: Obtenga información sobre el funcionamiento de la autenticación NTLM predeterminada, la autenticación NTLM no predeterminada y la autenticación Kerberos en una aplicación de .NET Framework.
ms.date: 03/30/2017
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
ms.openlocfilehash: 3fcd39f5414bca9bfcb368f6962ae36891458151
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262832"
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
> La autenticación NTLM no funciona a través de un servidor proxy.  
  
## <a name="see-also"></a>Vea también

- [Autenticación básica e implícita](basic-and-digest-authentication.md)
- [Autenticación de Internet](internet-authentication.md)
