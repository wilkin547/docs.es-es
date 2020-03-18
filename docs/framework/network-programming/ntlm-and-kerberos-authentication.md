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
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="350a5-102">Autenticación de NTLM y Kerberos</span><span class="sxs-lookup"><span data-stu-id="350a5-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="350a5-103">La autenticación NTLM predeterminada y la autenticación Kerberos usan las credenciales de usuario de Microsoft Windows NT asociadas a la aplicación que realiza la llamada para intentar la autenticación con el servidor.</span><span class="sxs-lookup"><span data-stu-id="350a5-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="350a5-104">Cuando se usa la autenticación NTLM no predeterminada, la aplicación establece el tipo de autenticación en NTLM y usa un objeto <xref:System.Net.NetworkCredential> para pasar el nombre de usuario, la contraseña y el dominio al host, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="350a5-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="350a5-105">Las aplicaciones que necesitan conectarse a los servicios de Internet mediante las credenciales del usuario de la aplicación pueden hacerlo con las credenciales predeterminadas del usuario, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="350a5-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="350a5-106">El módulo de autenticación de negociación determina si el servidor remoto está usando la autenticación NTLM o Kerberos, y envía la respuesta adecuada.</span><span class="sxs-lookup"><span data-stu-id="350a5-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="350a5-107">La autenticación NTLM no funciona a través de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="350a5-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350a5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="350a5-108">See also</span></span>

- [<span data-ttu-id="350a5-109">Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="350a5-109">Basic and Digest Authentication</span></span>](basic-and-digest-authentication.md)
- [<span data-ttu-id="350a5-110">Autenticación de Internet</span><span class="sxs-lookup"><span data-stu-id="350a5-110">Internet Authentication</span></span>](internet-authentication.md)
