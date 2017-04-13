---
title: "Principal and Identity Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WindowsIdentity objects"
  - "GenericIdentity objects"
  - "GenericPrincipal objects"
  - "identity objects, about identity objects"
  - "security [.NET Framework], identity objects"
  - "principal objects, about principal objects"
  - "security [.NET Framework], principals"
  - "WindowsPrincipal objects"
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Principal and Identity Objects
El código administrado puede detectar la identidad o el rol de una entidad de seguridad a través de un objeto [Principal](frlrfSystemSecurityPrincipalIPrincipalClassTopic), que contiene una referencia a un objeto [Identity](frlrfSystemSecurityPrincipalIIdentityClassTopic).  Puede ser útil la comparación de objetos de identidad y entidad de seguridad con conceptos familiares, como las cuentas de grupo y usuario.  En la mayoría de los entornos de red, las cuentas de usuario representan a personas o programas, mientras que las cuentas de grupo representan a ciertas categorías de usuarios y los derechos que poseen.  De forma similar, los objetos de identidad de .NET Framework representan a usuarios, mientras que los roles representan pertenencias y contextos de seguridad.  En .NET Framework, el objeto de entidad de seguridad encapsula un objeto de identidad y un rol. Las aplicaciones .NET Framework conceden derechos a la entidad de seguridad basándose en su identidad o, lo que es más normal, en su pertenencia a un rol.  
  
## Objetos Identity  
 El objeto de identidad encapsula información relativa al usuario o la entidad que se van a validar.  En su nivel más básico, los objetos de identidad contienen un nombre y un tipo de autenticación.  El nombre puede ser un nombre de usuario o el nombre de una cuenta de Windows, mientras que el tipo de autenticación puede ser un protocolo de inicio de admisión admitido, como Kerberos V5, o un valor personalizado.  .NET Framework define un objeto <xref:System.Security.Principal.GenericIdentity> que se puede utilizar para la mayoría de los escenarios de inicio de sesión personalizados y un objeto <xref:System.Security.Principal.WindowsIdentity> más especializado que se puede utilizar cuando se desea que la aplicación se base en una autenticación de Windows.  Además, se puede definir la clase de identidad propia que encapsula la información personalizada del usuario.  
  
 La interfaz <xref:System.Security.Principal.IIdentity> define propiedades para el acceso a un nombre y un tipo de autenticación, como Kerberos V5 o NTLM.  Todas las clases **Identity** implementan la interfaz **IIdentity**.  No hay una relación necesaria entre un objeto **Identity** y el símbolo \(token\) de proceso de Windows NT bajo el cual se está ejecutando actualmente un subproceso.  No obstante, si el objeto **Identity** es un objeto **WindowsIdentity**, se supone que la identidad representa un token de seguridad de Windows NT.  
  
## Objetos Principal  
 El objeto de entidad de seguridad representa el contexto de seguridad bajo el cual se ejecuta código.  Las aplicaciones que implementan seguridad basada en roles conceden derechos tomando como base el rol asociado a un objeto de entidad de seguridad.  De forma similar a los objetos de identidad, .NET Framework proporciona un objeto <xref:System.Security.Principal.GenericPrincipal> y un objeto <xref:System.Security.Principal.WindowsPrincipal>.  También se pueden definir clases principales personalizadas propias.  
  
 La interfaz <xref:System.Security.Principal.IPrincipal> define una propiedad para el acceso a un objeto **Identity** asociado, así como un método para determinar si el usuario identificado por el objeto **Principal** es miembro de un rol dado.  Todas las clases **Principal** implementan la interfaz **IPrincipal**, así como las propiedades y métodos adicionales necesarios.  Por ejemplo, Common Language Runtime proporciona la clase **WindowsPrincipal**, que implementa funcionalidad adicional para asignar a roles la pertenencia a un grupo de Windows NT o Windows 2000.  
  
 Un objeto **Principal** se enlaza a un objeto de contexto de llamada \(<xref:System.Runtime.Remoting.Messaging.CallContext>\) dentro de un dominio de aplicación \(<xref:System.AppDomain>\).  Un contexto de llamada predeterminado se crea siempre con cada dominio **AppDomain** nuevo, por lo que siempre hay un contexto de llamada disponible para aceptar el objeto **Principal**.  Cuando se crea un subproceso nuevo, también se crea un objeto **CallContext** para el subproceso.  La referencia del objeto **Principal** se copia automáticamente desde el subproceso creador en el objeto **CallContext** del subproceso nuevo.  Si el motor en tiempo de ejecución no puede determinar qué objeto **Principal** pertenece al creador del subproceso, sigue la directiva predeterminada para la creación de objetos **Principal** e **Identity**.  
  
 Una directiva específica de dominio de aplicación configurable define las reglas para decidir qué tipo de objeto **Principal** se ha de asociar a un dominio de aplicación nuevo.  Cuando la directiva de seguridad lo permite, el motor en tiempo de ejecución puede crear objetos **Principal** e **Identity** que reflejan el símbolo \(token\) de sistema operativo asociado al subproceso actual de ejecución.  De forma predeterminada, el motor en tiempo de ejecución utiliza objetos **Principal** e **Identity** que representan a usuarios no autenticados,  pero no los crea hasta que el código intenta el acceso a ellos.  
  
 El código de confianza que crea un dominio de aplicación puede establecer la directiva de dominio de aplicación que controla la construcción de los objetos **Principal** e **Identity** predeterminados.  Esta directiva específica de dominio de aplicación se aplica a todos los subprocesos de ejecución de dicho dominio.  Un host de confianza no administrado tiene la capacidad inherente de establecer esta directiva, pero el código administrado que la establece debe tener el permiso <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName> para controlar la directiva de dominio.  
  
 Cuando se transmite un objeto **Principal** a través de dominios de aplicación, pero dentro del mismo proceso \(y, por tanto, en el mismo equipo\), la infraestructura de comunicación remota copia una referencia en el objeto **Principal** asociado al contexto de quien efectúa una llamada en el contexto de quien la recibe.  
  
## Vea también  
 [How to: Create a WindowsPrincipal Object](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)   
 [How to: Create GenericPrincipal and GenericIdentity Objects](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)   
 [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Impersonating and Reverting](../../../docs/standard/security/impersonating-and-reverting.md)   
 [Role\-Based Security](../../../docs/standard/security/role-based-security.md)   
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)