---
title: Mecanismos de control de acceso
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: b423dac4d8324069eb1825666419b23b5afdca63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185492"
---
# <a name="access-control-mechanisms"></a>Mecanismos de control de acceso
Puede controlar el acceso de varias maneras con Windows Communication Foundation (WCF). Este tema aborda brevemente los diversos mecanismos y proporciona sugerencias sobre cuándo utilizar cada uno; está destinado a ayudarle a seleccionar el mecanismo correcto a utilizar. Las tecnologías de acceso están listadas por orden de complejidad. La más simple es <xref:System.Security.Permissions.PrincipalPermissionAttribute>; la más compleja es el modelo de identidad.  
  
 Además de estos mecanismos, la suplantación y delegación con WCF se explica en [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> se utiliza para restringir el acceso a un método de servicio. Cuando el atributo se aplica a un método, se puede usar para exigir la identidad o pertenencia de un autor de llamadas específico en un grupo de Windows o ASP.NET rol. Si el cliente se autentica utilizando un certificado X.509, se le proporciona una identidad primaria que está compuesta del nombre de sujeto más la huella digital del certificado.  
  
 Utilice <xref:System.Security.Permissions.PrincipalPermissionAttribute> para controlar el acceso a los recursos en el equipo en el que el servicio se está ejecutando y si los usuarios del servicio siempre formarán parte del mismo dominio de Windows en el que el servicio se está ejecutando. Puede crear con facilidad grupos de Windows que hayan especificado niveles de acceso (como ninguno, de solo lectura o lectura y escritura).  
  
 Para obtener más información sobre el uso del atributo, vea Cómo: restringir el [acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). Para obtener más información acerca de la identidad, vea [Identidad de servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>Proveedor de pertenencia a ASP.NET  
 Una característica de ASP.NET es el proveedor de membresía. Aunque el proveedor de pertenencia no es técnicamente un mecanismo de control de acceso, permite controlar el acceso al servicio limitando el conjunto de posibles identidades que pueden tener acceso al punto de conexión del servicio. La característica de pertenencia incluye una base de datos que se puede rellenar con combinaciones de nombre de usuario/contraseña que permitan a los usuarios de un sitio Web establecer cuentas en el sitio. Para tener acceso a un servicio que usa el proveedor de pertenencia, un usuario debe iniciar sesión con su nombre de usuario y contraseña.  
  
> [!NOTE]
> Primero debe rellenar la base de datos mediante la característica ASP.NET antes de que un servicio WCF pueda usarla con fines de autorización.  
  
 También puede usar la característica de pertenencia si ya tiene una base de datos de pertenencia de un sitio Web de ASP.NET existente y desea permitir que los mismos usuarios usen el servicio, autorizado con los mismos nombres de usuario y contraseñas.  
  
 Para obtener más información acerca del uso de la característica de pertenencia en un servicio WCF, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)de pertenencia .  
  
## <a name="aspnet-role-provider"></a>Proveedor de roles ASP.NET  
 Otra característica de ASP.NET es la capacidad de administrar la autorización mediante roles. El ASP.NET proveedor de roles permite a un desarrollador crear roles para los usuarios y asignar cada usuario a un rol o roles. Al igual que con el proveedor de pertenencia, los roles y las asignaciones se almacenan en una base de datos y se pueden rellenar mediante las herramientas proporcionadas por una implementación determinada del ASP.NET proveedor de roles. Al igual que con la característica de pertenencia, los desarrolladores de WCF pueden usar la información de la base de datos para autorizar a los usuarios de servicio por roles. Por ejemplo, pueden utilizar el proveedor de funciones en combinación con el mecanismo de control de acceso `PrincipalPermissionAttribute` descrito anteriormente.  
  
 También puede usar el ASP.NET proveedor de roles si tiene una base de datos de proveedor de roles de ASP.NET existente y desea usar el mismo conjunto de reglas y asignaciones de usuario en el servicio WCF.  
  
 Para obtener más información sobre el uso de la característica de proveedor de roles, vea [Cómo: usar el proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)de roles de ASP.NET con un servicio .  
  
## <a name="authorization-manager"></a>Administrador de autorización  
 Otra característica combina el Administrador de autorización (AzMan) con el proveedor de roles ASP.NET para autorizar a los clientes. Cuando ASP.NET aloja un servicio web, AzMan se puede integrar en la aplicación para que la autorización del servicio se realice a través de AzMan. ASP.NET administrador de roles proporciona una API que le permite administrar roles de aplicación, agregar y quitar usuarios de roles y comprobar la pertenencia a roles, pero no permite consultar si un usuario está autorizado a realizar una tarea u operación con nombre. AzMan le permite definir operaciones individuales y combinarlas en tareas. Con AZMan, además de las comprobaciones de la función, también puede comprobar si un usuario puede realizar una tarea. La asignación de funciones y la autorización de tareas se pueden configurar fuera de la aplicación o se pueden realizar mediante programación dentro de la aplicación. El complemento Microsoft Management Console (MMC) de administración de AzMan permite a los administradores cambiar las tareas que una función puede realizar en tiempo de ejecución y administrar la pertenencia de funciones de cada usuario.  
  
 También puede utilizar AzMan y el proveedor de roles ASP.NET si ya tiene acceso a una instalación de AzMan existente y desea autorizar a los usuarios del servicio mediante las características de la combinación de AzMan/proveedor de roles.  
  
 Para obtener más información acerca de AzMan y el proveedor de roles ASP.NET, vea Cómo: usar el Administrador de [autorización (AzMan) con ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)). Para obtener más información acerca del uso de AzMan y el proveedor de roles para servicios WCF, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)de roles de administrador de autorización con un servicio .  
  
## <a name="identity-model"></a>Modelo de identidad  
 El modelo de identidad es un conjunto de API que le permiten administrar demandas y directivas para autorizar a los clientes. Con el modelo de identidad, puede examinar cada demanda contenida en credenciales que el llamador utiliza para autenticarse a sí mismo para el servicio, comparar las demandas con el conjunto de directivas para el servicio y conceder o denegar acceso basándose en la comparación.  
  
 Utilice el modelo de identidad si necesita un control preciso y la capacidad de establecer criterios concretos antes de conceder el acceso. Por ejemplo, al utilizar <xref:System.Security.Permissions.PrincipalPermissionAttribute>, el criterio simplemente es que la identidad del usuario se pueda autenticar y pertenezca a una función concreta. En cambio, utilizando el modelo de identidad, puede crear una directiva que establezca que el usuario debe ser mayor de 18 años y poseer una licencia de conducir válida antes de que se le permita ver un documento.  
  
 Un ejemplo donde puede beneficiarse del control de acceso basado en notificaciones del modelo de identidad es al usar credenciales de federación en el escenario de token emitido. Para obtener más información acerca de la federación y los tokens emitidos, vea [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Para obtener más información sobre el modelo de identidad, vea [Administrar notificaciones y autorización con el modelo](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)de identidad .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
