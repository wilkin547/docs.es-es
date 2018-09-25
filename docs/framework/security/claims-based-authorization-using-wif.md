---
title: Autorización basada en notificaciones con WIF
ms.date: 03/30/2017
ms.assetid: e24000a3-8fd8-4c0e-bdf0-39882cc0f6d8
author: BrucePerlerMS
ms.openlocfilehash: c13ea5c9f2f62c9c01139741d06de35dd2ff4be1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088118"
---
# <a name="claims-based-authorization-using-wif"></a>Autorización basada en notificaciones con WIF
En una aplicación de usuario de confianza, la autorización determina los recursos a los que una identidad autenticada puede tener acceso y las operaciones que puede realizar en estos. Una autorización incorrecta o débil da lugar a la revelación de información y a la alteración de los datos. En este tema se describen distintos enfoques para implementar la autorización para aplicaciones web y servicios Web ASP.NET compatibles con notificaciones mediante Windows Identity Foundation (WIF) y un servicio de token de seguridad (STS), por ejemplo, Microsoft Azure Access Control Service (ACS).  
  
## <a name="overview"></a>Información general  
 Desde su primera versión, .NET Framework ha ofrecido un mecanismo flexible para implementar la autorización. Este mecanismo se basa en dos sencillas interfaces: **IPrincipal** e **IIdentity**. Las implementaciones concretas de **IIdentity** representan a un usuario autenticado. Por ejemplo, la implementación de **WindowsIdentity** representa a un usuario autenticado por Active Directory y **GenericIdentity** representa a un usuario cuya identidad se comprueba mediante un proceso de autenticación personalizado. Las implementaciones concretas de **IPrincipal** ayudan a comprobar los permisos mediante roles según el almacén de roles. Por ejemplo, **WindowsPrincipal** comprueba la pertenencia a grupos de Active Directory de **WindowsIdentity**. Esta comprobación se realiza al llamar al método **IsInRole** en la interfaz **IPrincipal**. La comprobación del acceso basada en roles se denomina control de acceso basado en roles (RBAC). Para más información, vea [Control de acceso basado en roles](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_1).  Las notificaciones se pueden usar para proporcionar información sobre roles a fin de admitir mecanismos de autorización basados en roles.  
  
 Asimismo, pueden usarse para permitir decisiones de autorización más complicadas más allá de los roles. Las notificaciones pueden basarse en prácticamente cualquier información sobre el usuario: edad, código postal, talla de calzado, etc. Un mecanismo de control de acceso basado en notificaciones arbitrarias se denomina autorización basada en notificaciones. Para más información, vea [Autorización basada en notificaciones](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_2).  
  
<a name="BKMK_1"></a>   
## <a name="role-based-access-control"></a>Control de acceso basado en roles  
 El control de acceso basado en roles (RBAC) es un enfoque de autorización en el cual una aplicación basada en roles de usuario administra y aplica los permisos de usuario. Si un usuario tiene un rol necesario para realizar una acción, se concede el acceso; de lo contrario, se deniega.  
  
### <a name="iprincipalisinrole-method"></a>Método IPrincipal.IsInRole  
 Para implementar el enfoque RBAC en las aplicaciones para notificaciones, use el método **IsInRole()** de la interfaz **IPrincipal**, de la misma forma en que lo haría en aplicaciones no compatibles con notificaciones. Existen varias formas de usar el método **IsInRole()**:  
  
-   Al llamar explícitamente a **IPrincipal.IsInRole("Administrator")**. En este enfoque, el resultado es un valor booleano. Úselo en las instrucciones condicionales. Se puede usar arbitrariamente en cualquier parte del código.  
  
-   Mediante la petición de seguridad **PrincipalPermission.Demand()**. En este enfoque, se produce una excepción en caso de que la petición no se cumpla. Esta debe ajustarse a la estrategia de control de excepciones. La generación de excepciones es mucho más costosa desde el punto de vista del rendimiento que la devolución del valor booleano. Se puede usar en cualquier parte del código.  
  
-   Al usar los atributos declarativos **[PrincipalPermission(SecurityAction.Demand, Role = "Administrator")]**. Este enfoque se denomina declarativo porque se usa para representar métodos. No se puede usar en bloques de código dentro de implementaciones de método. Se produce una excepción en caso de que no se cumpla la petición. Debe asegurarse de que se ajuste a la estrategia de control de excepciones.  
  
-   Al usar la autorización para URL, mediante la sección **\<authorization>** de **web.config**. Este enfoque resulta conveniente al administrar la autorización en un nivel de dirección URL. Es el nivel más amplio de todos los mencionados anteriormente. La ventaja de este enfoque es que los cambios se realizan en el archivo de configuración, lo que significa que el código no debe compilarse para beneficiarse del cambio.  
  
### <a name="expressing-roles-as-claims"></a>Expresar roles como notificaciones  
 Cuando se llama al método **IsInRole()**, se comprueba si el usuario actual tiene ese rol. En las aplicaciones para notificaciones, el rol se expresa mediante un tipo de notificación de rol que debe estar disponible en el token. El tipo de notificación de rol se expresa mediante el URI siguiente:  
  
 http://schemas.microsoft.com/ws/2008/06/identity/claims/role  
  
 Hay varias formas de enriquecer un token con un tipo de notificación de rol:  
  
-   **Durante la emisión de tokens**. Cuando se autentica un usuario, tanto el STS del proveedor de identidad como un proveedor de federación, por ejemplo, Microsoft Azure Access Control Service (ACS), pueden emitir la notificación de rol.  
  
-   **Al transformar notificaciones arbitrarias en notificaciones de tipo de rol mediante ClaimsAuthenticationManager**. ClaimsAuthenticationManager es un componente que se distribuye como parte de WIF. Permite interceptar las solicitudes al iniciar una aplicación, inspeccionar tokens y transformarlos mediante la adición, cambio o eliminación de notificaciones. Para obtener más información acerca de cómo usar ClaimsAuthenticationManager para transformar notificaciones, consulte [How To: Implement basado en rol Access Control (RBAC) de notificaciones compatible con aplicaciones ASP.NET mediante WIF y ACS](https://go.microsoft.com/fwlink/?LinkID=247445).  
  
-   **Al asignar notificaciones arbitrarias a un tipo de rol mediante la sección de configuración samlSecurityTokenRequirement**: enfoque declarativo donde la transformación de las notificaciones se lleva a cabo únicamente a través de la configuración sin necesidad de codificación.  
  
<a name="BKMK_2"></a>   
## <a name="claims-based-authorization"></a>Autorización basada en notificaciones  
 La autorización basada en notificaciones es un enfoque donde la decisión sobre la autorización para conceder o denegar el acceso se basa en lógica arbitraria que usa los datos disponibles en las notificaciones para tomar la decisión. Recuerde que, en el caso del RBAC, la única notificación que se usaba era la de tipo de rol para comprobar si el usuario pertenecía o no a un rol concreto. Para ilustrar el proceso de toma de decisiones de autorización mediante un enfoque basado en notificaciones, tenga en cuenta los pasos siguientes:  
  
1.  La aplicación recibe una solicitud que requiere la autenticación del usuario.  
  
2.  WIF redirige al usuario al proveedor de identidad correspondiente. Una vez autenticado, la solicitud de la aplicación se realiza con un token de seguridad asociado que representa al usuario y contiene notificaciones sobre este. WIF asocia dichas notificaciones a la entidad de seguridad que representa al usuario.  
  
3.  La aplicación pasa las notificaciones al mecanismo de lógica de decisión. Puede ser código en memoria, una llamada a un servicio Web, una consulta a una base de datos, un motor de reglas sofisticado o mediante ClaimsAuthorizationManager.  
  
4.  El mecanismo de decisión calcula el resultado en función de las notificaciones.  
  
5.  El acceso se concede si el resultado es true y se deniega si es false. Por ejemplo, la regla podría ser que el usuario tenga 21 años o más y resida en el estado de Washington.  
  
 <xref:System.Security.Claims.ClaimsAuthorizationManager> es útil para exteriorizar la lógica de decisión de la autorización basada en notificaciones de las aplicaciones. ClaimsAuthorizationManager es un componente de WIF que se distribuye como parte de .NET 4.5. ClaimsAuthorizationManager permite interceptar solicitudes entrantes e implementar la lógica deseada para tomar decisiones de autorización en función de las notificaciones entrantes. Esto es importante cuando es necesario cambiar la lógica de autorización. En ese caso, el uso de ClaimsAuthorizationManager no afectará a la integridad de la aplicación y se reducirá la probabilidad de un error de aplicación como resultado del cambio. Para más información sobre cómo usar ClaimsAuthorizationManager para implementar el control de acceso basado en notificaciones, vea [Procedimiento: Implementación de autorización de notificaciones en aplicaciones ASP.Net compatible con notificaciones mediante WIF y ACS](https://go.microsoft.com/fwlink/?LinkID=247446).
