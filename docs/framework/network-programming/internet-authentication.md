---
title: "Autenticaci&#243;n de Internet | Microsoft Docs"
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
  - "IAuthenticationModule (interfaz)"
  - "ICredentialLookup (interfaz)"
  - "CredentialCache (clase), acerca de la clase CredentialCache"
  - "recibir datos, autenticación"
  - "AuthenticationManager (clase), acerca de la clase AuthenticationManager"
  - "Internet, autenticación"
  - "enviar datos, autenticación"
  - "recursos de red, autenticación"
  - "autenticación de usuario, clases para autenticación"
  - "NetworkCredential (clase), acerca de la clase NetworkCredential"
  - "autenticación de cliente, clases para autenticación"
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Autenticaci&#243;n de Internet
Las clases de <xref:System.Net> admiten una variedad de mecanismos de autenticación del cliente, incluidos los métodos de autenticación estándar de internet básica, implícita, operan, NTLM, y los métodos de autenticación Kerberos, así como personalizados que puede crear.  
  
 Las credenciales de autenticación se almacenan en las clases de <xref:System.Net.NetworkCredential> y de <xref:System.Net.CredentialCache> , que implementa la interfaz de <xref:System.Net.ICredentials> .  Cuando una de estas clases se consulta para las credenciales, devuelve una instancia de la clase de **NetworkCredential** .  El proceso de autenticación es administrado por la clase de <xref:System.Net.AuthenticationManager> , y el proceso de autenticación real realiza una clase de módulo de autenticación que implemente la interfaz de <xref:System.Net.IAuthenticationModule> .  Debe registrar un módulo de autenticación personalizada con **AuthenticationManager** antes de poderse utilizar; los módulos para el básica, implícita, operan, NTLM, y los métodos de autenticación Kerberos se registran de forma predeterminada.  
  
 **NetworkCredential** almacena un conjunto de credenciales asociadas a un único recurso de internet identificado por un identificador URI y las devuelve en respuesta a cualquier llamada al método de <xref:System.Net.NetworkCredential.GetCredential%2A> .  La clase de **NetworkCredential** se utiliza normalmente en aplicaciones que tienen acceso a un número limitado de recursos de internet o las aplicaciones que utilizan el mismo conjunto de credenciales en todos los casos.  
  
 La clase de **CredentialCache** almacena una colección de credenciales para los distintos recursos web.  Cuando se llama al método de <xref:System.Net.CredentialCache.GetCredential%2A> , **CredentialCache** devuelve el conjunto adecuado de credenciales, determinado por el identificador URI del recurso web y el esquema de autenticación solicitado.  Las aplicaciones que utilizan diversos recursos de internet con diferentes esquemas de autenticación se benefician de utilizar la clase de **CredentialCache** , ya que almacena todas las credenciales y las proporcionan como se solicitan.  
  
 Cuando un recurso de internet solicita la autenticación, el método de <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=fullName> envía <xref:System.Net.WebRequest> a **AuthenticationManager** junto con la solicitud para las credenciales.  La solicitud se autentica según el proceso siguiente:  
  
1.  **AuthenticationManager** llama al método de <xref:System.Net.IAuthenticationModule.Authenticate%2A> en cada uno de los módulos registrados de autenticación en el orden que se registraron.  **AuthenticationManager** utiliza el primer módulo que no devuelve **null** para realizar el proceso de autenticación.  Detalles del proceso varían según el tipo de módulo de autenticación existente.  
  
2.  Cuando se completa el proceso de autenticación, el módulo de autenticación devuelve <xref:System.Net.Authorization> a **WebRequest** que contiene la información necesaria para tener acceso al recurso de internet.  
  
 Algunos esquemas de autenticación pueden autenticar un usuario sin crear primero una solicitud para un recurso.  Una aplicación puede ahorrar tiempo preauthenticating al usuario al recurso, lo eliminando por lo menos una acción de ida y vuelta al servidor.  O bien, puede realizar la autenticación durante el inicio del programa para ser mayor capacidad del usuario más adelante.  Los esquemas de autenticación que pueden utilizar el preauthentication establecen la propiedad de [CanPreAuthenticate](frlrfsystemnetiauthenticationmoduleclasspreauthenticatetopic) a **true**.  
  
## Vea también  
 [Autenticación básica e implícita](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Autenticación de NTLM y Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Seguridad en la programación para redes](../../../docs/framework/network-programming/security-in-network-programming.md)