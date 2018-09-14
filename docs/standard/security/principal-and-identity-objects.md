---
title: Objetos Principal e Identity
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- WindowsIdentity objects
- GenericIdentity objects
- GenericPrincipal objects
- identity objects, about identity objects
- security [.NET Framework], identity objects
- principal objects, about principal objects
- security [.NET Framework], principals
- WindowsPrincipal objects
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8c7616a3187cd5fa28f231dffd15b0bfeea4b7f
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519726"
---
# <a name="principal-and-identity-objects"></a>Objetos Principal e Identity
Código administrado puede detectar la identidad o el rol de una entidad de seguridad a través de un <xref:System.Security.Principal.IPrincipal> objeto, que contiene una referencia a un <xref:System.Security.Principal.IIdentity> objeto. La comparación de objetos Identity y Principal puede resultar útil en conceptos familiares, como cuentas de usuario y de grupo. En la mayoría de los entornos de red, las cuentas de usuario representan a personas o programas, mientras que las cuentas de grupo representan a ciertas categorías de usuarios y los derechos que poseen. De forma similar, los objetos Identity de .NET Framework representan a usuarios, mientras que los roles representan pertenencias y contextos de seguridad. En .NET Framework, el objeto Principal encapsula un objeto Identity y un rol. Las aplicaciones .NET Framework conceden derechos a la entidad de seguridad basándose en su identidad o, lo que es más normal, en su pertenencia a un rol.  
  
## <a name="identity-objects"></a>Objetos Identity  
 El objeto Identity encapsula información sobre el usuario o la entidad que se está validando. En su nivel más básico, los objetos Identity contienen un nombre y un tipo de autenticación. El nombre puede ser un nombre de usuario o el nombre de una cuenta de Windows, mientras que el tipo de autenticación puede ser un protocolo de inicio de admisión admitido, como Kerberos V5, o un valor personalizado. .NET Framework define un <xref:System.Security.Principal.GenericIdentity> objeto que puede usarse para la mayoría de los escenarios de inicio de sesión personalizada y más especializado <xref:System.Security.Principal.WindowsIdentity> objeto que se puede usar cuando desee que la aplicación para que se basan en la autenticación de Windows. Además, puede definir la clase de identidad propia que encapsula la información personalizada del usuario.  
  
 El <xref:System.Security.Principal.IIdentity> interfaz define propiedades para tener acceso a un nombre y un tipo de autenticación, como Kerberos V5 o NTLM. Todas las clases **Identity** implementan la interfaz **IIdentity**. No hay una relación necesaria entre un objeto **Identity** y el token de proceso de Windows NT bajo el cual se está ejecutando actualmente un subproceso. No obstante, si el objeto **Identity** es un objeto **WindowsIdentity**, se supone que la identidad representa un token de seguridad de Windows NT.  
  
## <a name="principal-objects"></a>Objetos Principal  
 El objeto Principal representa el contexto de seguridad bajo el cual se ejecuta código. Las aplicaciones que implementan seguridad basada en roles conceden derechos tomando como base el rol asociado a un objeto Principal. Al igual que los objetos de identidad, .NET Framework proporciona un <xref:System.Security.Principal.GenericPrincipal> objeto y un <xref:System.Security.Principal.WindowsPrincipal> objeto. También puede definir sus propias clases de entidad de seguridad personalizadas.  
  
 El <xref:System.Security.Principal.IPrincipal> interfaz define una propiedad para tener acceso a un asociado **identidad** objeto, así como un método para determinar si el usuario identificado por el **Principal** objeto es un miembro de un rol determinado. Todas las clases **Principal** implementan la interfaz **IPrincipal**, así como las propiedades y métodos adicionales necesarios. Por ejemplo, Common Language Runtime proporciona la clase **WindowsPrincipal**, que implementa funcionalidad adicional para asignar a roles la pertenencia a un grupo de Windows NT o Windows 2000.  
  
 Un **Principal** objeto está enlazado a un contexto de llamada (<xref:System.Runtime.Remoting.Messaging.CallContext>) objeto dentro de un dominio de aplicación (<xref:System.AppDomain>). Un contexto de llamada predeterminado se crea siempre con cada dominio **AppDomain** nuevo, por lo que siempre hay un contexto de llamada disponible para aceptar el objeto **Principal**. Cuando se crea un subproceso nuevo, también se crea un objeto **CallContext** para el subproceso. La referencia del objeto **Principal** se copia automáticamente desde el subproceso creador en el objeto **CallContext** del subproceso nuevo. Si el tiempo de ejecución no puede determinar qué objeto **Principal** pertenece al creador del subproceso, sigue la directiva predeterminada para la creación de objetos **Principal** e **Identity**.  
  
 Una directiva específica de dominio de aplicación configurable define las reglas para decidir qué tipo de objeto **Principal** se ha de asociar a un dominio de aplicación nuevo. Cuando la directiva de seguridad lo permite, el tiempo de ejecución puede crear objetos **Principal** e **Identity** que reflejan el token de sistema operativo asociado al subproceso actual de ejecución. De forma predeterminada, el tiempo de ejecución utiliza objetos **Principal** e **Identity** que representan a usuarios no autenticados. El tiempo de ejecución no crea estos objetos **Principal** y **Identity** predeterminados hasta que el código trata de tener acceso a ellos.  
  
 El código de confianza que crea un dominio de aplicación puede establecer la directiva de dominio de aplicación que controla la construcción de los objetos **Principal** e **Identity** predeterminados. Esta directiva específica de dominio de aplicación se aplica a todos los subprocesos de ejecución de dicho dominio. Un host de confianza no administrado tiene inherente de la capacidad de establecer esta directiva, pero el código administrado que se establece esta directiva debe tener el <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> para controlar la directiva de dominio.  
  
 Cuando se transmite un objeto **Principal** a través de dominios de aplicación, pero dentro del mismo proceso (y, por tanto, en el mismo equipo), la infraestructura de comunicación remota copia una referencia en el objeto **Principal** asociado al contexto de quien efectúa una llamada en el contexto de quien la recibe.  
  
## <a name="see-also"></a>Vea también

- [Crear un objeto WindowsPrincipal](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)  
- [Crear objetos GenericPrincipal y GenericIdentity](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)  
- [Reemplazar un objeto Principal](../../../docs/standard/security/replacing-a-principal-object.md)  
- [Suplantar y revertir](../../../docs/standard/security/impersonating-and-reverting.md)  
- [Seguridad basada en roles](../../../docs/standard/security/role-based-security.md)  
- [Conceptos clave de seguridad](../../../docs/standard/security/key-security-concepts.md)
