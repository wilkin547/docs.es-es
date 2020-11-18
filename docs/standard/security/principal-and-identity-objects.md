---
title: Objetos Principal e Identity
description: Lea acerca de los objetos de identidad, que representan a los usuarios de .NET. También puede leer sobre los objetos de entidad de seguridad, que encapsulan un objeto de identidad & un rol.
ms.date: 07/15/2020
helpviewer_keywords:
- WindowsIdentity objects
- GenericIdentity objects
- GenericPrincipal objects
- identity objects, about identity objects
- security [.NET], identity objects
- principal objects, about principal objects
- security [.NET], principals
- WindowsPrincipal objects
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
ms.openlocfilehash: cfda506fc29e9a86e97b3c99faf2d4155c894f03
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824244"
---
# <a name="principal-and-identity-objects"></a>Objetos Principal e Identity

> [!NOTE]
> Este artículo se aplica a Windows.
>
> Para obtener información sobre ASP.NET Core, consulte [ASP.net Core Security](/aspnet/core/security/).

El código administrado puede detectar la identidad o el rol de una entidad de seguridad a través de un <xref:System.Security.Principal.IPrincipal> objeto, que contiene una referencia a un <xref:System.Security.Principal.IIdentity> objeto. La comparación de objetos Identity y Principal puede resultar útil en conceptos familiares, como cuentas de usuario y de grupo. En la mayoría de los entornos de red, las cuentas de usuario representan a personas o programas, mientras que las cuentas de grupo representan a ciertas categorías de usuarios y los derechos que poseen. De forma similar, los objetos de identidad de .NET representan a los usuarios, mientras que los roles representan pertenencias y contextos de seguridad. En .NET, el objeto principal encapsula un objeto de identidad y un rol. Las aplicaciones .NET conceden derechos a la entidad de seguridad en función de su identidad o, más comúnmente, su pertenencia a roles.  
  
## <a name="identity-objects"></a>Objetos Identity

El objeto Identity encapsula información sobre el usuario o la entidad que se está validando. En su nivel más básico, los objetos Identity contienen un nombre y un tipo de autenticación. El nombre puede ser un nombre de usuario o el nombre de una cuenta de Windows, mientras que el tipo de autenticación puede ser un protocolo de inicio de admisión admitido, como Kerberos V5, o un valor personalizado. .NET define un <xref:System.Security.Principal.GenericIdentity> objeto que se puede usar para la mayoría de los escenarios de inicio de sesión personalizados y un objeto más especializado <xref:System.Security.Principal.WindowsIdentity> que se puede usar cuando se desea que la aplicación se base en la autenticación de Windows. Además, puede definir la clase de identidad propia que encapsula la información personalizada del usuario.  
  
La <xref:System.Security.Principal.IIdentity> interfaz define las propiedades para tener acceso a un nombre y un tipo de autenticación, como Kerberos V5 o NTLM. Todas las clases **Identity** implementan la interfaz **IIdentity**. No hay una relación necesaria entre un objeto **Identity** y el token de proceso de Windows NT bajo el cual se está ejecutando actualmente un subproceso. No obstante, si el objeto **Identity** es un objeto **WindowsIdentity**, se supone que la identidad representa un token de seguridad de Windows NT.  
  
## <a name="principal-objects"></a>Objetos Principal

El objeto Principal representa el contexto de seguridad bajo el cual se ejecuta código. Las aplicaciones que implementan seguridad basada en roles conceden derechos tomando como base el rol asociado a un objeto Principal. De forma similar a los objetos de identidad, .NET proporciona un <xref:System.Security.Principal.GenericPrincipal> objeto y un <xref:System.Security.Principal.WindowsPrincipal> objeto. También puede definir sus propias clases de entidad de seguridad personalizadas.  
  
La <xref:System.Security.Principal.IPrincipal> interfaz define una propiedad para tener acceso a un objeto de **identidad** asociado, así como un método para determinar si el usuario identificado por el objeto de **entidad** de seguridad es miembro de un rol determinado. Todas las clases **Principal** implementan la interfaz **IPrincipal**, así como las propiedades y métodos adicionales necesarios. Por ejemplo, Common Language Runtime proporciona la clase **WindowsPrincipal**, que implementa funcionalidad adicional para asignar a roles la pertenencia a un grupo de Windows NT o Windows 2000.  
  
Un objeto de **entidad** de seguridad se enlaza a un <xref:System.Runtime.Remoting.Messaging.CallContext> objeto de contexto de llamada () dentro de un dominio de aplicación ( <xref:System.AppDomain> ). Un contexto de llamada predeterminado se crea siempre con cada dominio **AppDomain** nuevo, por lo que siempre hay un contexto de llamada disponible para aceptar el objeto **Principal**. Cuando se crea un subproceso nuevo, también se crea un objeto **CallContext** para el subproceso. La referencia del objeto **Principal** se copia automáticamente desde el subproceso creador en el objeto **CallContext** del subproceso nuevo. Si el tiempo de ejecución no puede determinar qué objeto **Principal** pertenece al creador del subproceso, sigue la directiva predeterminada para la creación de objetos **Principal** e **Identity**.  
  
Una directiva específica de dominio de aplicación configurable define las reglas para decidir qué tipo de objeto **Principal** se ha de asociar a un dominio de aplicación nuevo. Cuando la directiva de seguridad lo permite, el tiempo de ejecución puede crear objetos **Principal** e **Identity** que reflejan el token de sistema operativo asociado al subproceso actual de ejecución. De forma predeterminada, el tiempo de ejecución utiliza objetos **Principal** e **Identity** que representan a usuarios no autenticados. El tiempo de ejecución no crea estos objetos **Principal** y **Identity** predeterminados hasta que el código trata de tener acceso a ellos.  
  
El código de confianza que crea un dominio de aplicación puede establecer la directiva de dominio de aplicación que controla la construcción de los objetos **Principal** e **Identity** predeterminados. Esta directiva específica de dominio de aplicación se aplica a todos los subprocesos de ejecución de dicho dominio. Un host de confianza sin administrar inherentemente tiene la capacidad de establecer esta Directiva, pero el código administrado que establece esta Directiva debe tener el <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> para controlar la Directiva de dominio.  
  
Cuando se transmite un objeto **Principal** a través de dominios de aplicación, pero dentro del mismo proceso (y, por tanto, en el mismo equipo), la infraestructura de comunicación remota copia una referencia en el objeto **Principal** asociado al contexto de quien efectúa una llamada en el contexto de quien la recibe.  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para crear un objeto WindowsPrincipal](how-to-create-a-windowsprincipal-object.md)
- [Procedimiento para crear objetos GenericPrincipal y GenericIdentity](how-to-create-genericprincipal-and-genericidentity-objects.md)
- [Reemplazar un objeto Principal](replacing-a-principal-object.md)
- [Suplantar y revertir](impersonating-and-reverting.md)
- [Seguridad basada en roles](role-based-security.md)
- [Conceptos clave de seguridad](key-security-concepts.md)
- [Seguridad de ASP.NET Core](/aspnet/core/security/)
