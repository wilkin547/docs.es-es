---
title: Autenticación de NTLM y Kerberos
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
ms.openlocfilehash: 372101763bdd84b454e6e2db3ec6cf0ebdf3f991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180699"
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
