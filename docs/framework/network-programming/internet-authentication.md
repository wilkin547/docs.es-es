---
title: Autenticación de Internet
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
ms.openlocfilehash: 3e0b5cd58270cec758db5d4dad6f3ad48962921a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047918"
---
# <a name="internet-authentication"></a>Autenticación de Internet
Las clases <xref:System.Net> admiten diversos mecanismos de autenticación de cliente, incluidos los métodos de autenticación de Internet estándares básico, implícito, negociado, NTLM y autenticación Kerberos, así como métodos personalizados que puede crear.  
  
 Las credenciales de autenticación se almacenan en las clases <xref:System.Net.NetworkCredential> y <xref:System.Net.CredentialCache>, que implementan la interfaz <xref:System.Net.ICredentials>. Cuando se consulta una de estas clases para obtener las credenciales, devuelve una instancia de la clase **NetworkCredential**. El proceso de autenticación se administra mediante la clase <xref:System.Net.AuthenticationManager> y el proceso de autenticación real se realiza mediante una clase del módulo de autenticación que implementa la interfaz <xref:System.Net.IAuthenticationModule>. Debe registrar un módulo de autenticación personalizado con **AuthenticationManager** para que se pueda usar. Los módulos para los métodos de autenticación básico, implícito, negociado, NTLM y Kerberos están registrados de forma predeterminada.  
  
 **NetworkCredential** almacena un conjunto de credenciales asociadas a un único recurso de Internet identificado por un URI y las devuelve en respuesta a las llamadas al método <xref:System.Net.NetworkCredential.GetCredential%2A>. La clase **NetworkCredential** la suelen usar las aplicaciones que tienen acceso a un número limitado de recursos de Internet o las aplicaciones que usan el mismo conjunto de credenciales en todos los casos.  
  
 La clase **CredentialCache** almacena una colección de credenciales para diversos recursos web. Cuando se llama al método <xref:System.Net.CredentialCache.GetCredential%2A>, **CredentialCache** devuelve el conjunto apropiado de credenciales, según lo determinado por el URI del recurso web y el esquema de autenticación solicitado. Las aplicaciones que usan diversos recursos de Internet con diferentes esquemas de autenticación se benefician del uso de la clase **CredentialCache**, ya que almacena todas las credenciales y las proporciona cuando se solicitan.  
  
 Cuando un recurso de Internet solicita autenticación, el método <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> envía la <xref:System.Net.WebRequest> a **AuthenticationManager** junto con la solicitud de credenciales. La solicitud se autentica según el proceso siguiente:  
  
1. **AuthenticationManager** llama al método <xref:System.Net.IAuthenticationModule.Authenticate%2A> en cada uno de los módulos de autenticación registrados en el orden en el que se han registrado. **AuthenticationManager** usa el primer módulo que no devuelve **null** para llevar a cabo el proceso de autenticación. Los detalles del proceso varían según el tipo de módulo de autenticación implicado.  
  
2. Una vez completado el proceso de autenticación, el módulo de autenticación devuelve una <xref:System.Net.Authorization> a la **WebRequest** que contiene la información necesaria para tener acceso al recurso de Internet.  
  
 Algunos esquemas de autenticación pueden autenticar a un usuario sin realizar primero una solicitud para un recurso. Una aplicación puede ahorrar tiempo si autentica previamente al usuario con el recurso, lo que elimina al menos un recorrido de ida y vuelta al servidor. O bien, puede realizar la autenticación durante el inicio del programa para que responda mejor al usuario más adelante. Los esquemas de autenticación que pueden usar la autenticación previa establecen la propiedad <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> en **true**.  
  
## <a name="see-also"></a>Vea también

- [Autenticación básica e implícita](basic-and-digest-authentication.md)
- [Autenticación NTLM y Kerberos](ntlm-and-kerberos-authentication.md)
- [Seguridad en la programación para redes](security-in-network-programming.md)
