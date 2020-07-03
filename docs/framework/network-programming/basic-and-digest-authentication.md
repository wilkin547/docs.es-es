---
title: Autenticación básica e implícita
description: Obtenga información sobre el uso de la autenticación básica e implícita, en la que una aplicación proporciona un nombre de usuario y una contraseña en el objeto WebRequest que usa para solicitar datos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: 7772430b508b52a63d716550b69018385418c132
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502707"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="d26ae-103">Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="d26ae-103">Basic and Digest Authentication</span></span>
<span data-ttu-id="d26ae-104">La implementación <xref:System.Net> de autenticación básica e implícita se ajusta al estándar RFC2617 – HTTP Authentication: Basic and Digest Authentication (Autenticación HTTP: autenticación básica e implícita), disponible en el sitio web del [World Wide Web Consortium](https://www.w3.org).</span><span class="sxs-lookup"><span data-stu-id="d26ae-104">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="d26ae-105">Para usar autenticación básica e implícita, una aplicación debe proporcionar un nombre de usuario y una contraseña en la propiedad <xref:System.Net.WebRequest.Credentials%2A> del objeto <xref:System.Net.WebRequest> que usa para solicitar datos de Internet, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d26ae-105">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="d26ae-106">Los datos enviados con la autenticación básica e implícita no se cifran. Por tanto, los puede ver un adversario.</span><span class="sxs-lookup"><span data-stu-id="d26ae-106">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="d26ae-107">Además, las credenciales de autenticación básica (nombre de usuario y contraseña) se envían en texto no cifrado y se pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="d26ae-107">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26ae-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d26ae-108">See also</span></span>

- [<span data-ttu-id="d26ae-109">Autenticación NTLM y Kerberos</span><span class="sxs-lookup"><span data-stu-id="d26ae-109">NTLM and Kerberos Authentication</span></span>](ntlm-and-kerberos-authentication.md)
- [<span data-ttu-id="d26ae-110">Autenticación de Internet</span><span class="sxs-lookup"><span data-stu-id="d26ae-110">Internet Authentication</span></span>](internet-authentication.md)
