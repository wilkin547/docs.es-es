---
title: Mecanismos de control de acceso
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: daa16c0d4a0450a3a7fcaae0f7660e0092aa7ea5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293980"
---
# <a name="access-control-mechanisms"></a>Mecanismos de control de acceso

Puede controlar el acceso de varias maneras con Windows Communication Foundation (WCF). Este tema aborda brevemente los diversos mecanismos y proporciona sugerencias sobre cuándo utilizar cada uno; está destinado a ayudarle a seleccionar el mecanismo correcto a utilizar. Las tecnologías de acceso están listadas por orden de complejidad. La más simple es <xref:System.Security.Permissions.PrincipalPermissionAttribute>; la más compleja es el modelo de identidad.  
  
 Además de estos mecanismos, la suplantación y delegación con WCF se explican en [delegación y suplantación](delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  

 <xref:System.Security.Permissions.PrincipalPermissionAttribute> se utiliza para restringir el acceso a un método de servicio. Cuando el atributo se aplica a un método, se puede utilizar para solicitar la identidad o la pertenencia de un llamador específico en un rol de grupo o ASP.NET de Windows. Si el cliente se autentica utilizando un certificado X.509, se le proporciona una identidad primaria que está compuesta del nombre de sujeto más la huella digital del certificado.  
  
 Utilice <xref:System.Security.Permissions.PrincipalPermissionAttribute> para controlar el acceso a los recursos en el equipo en el que el servicio se está ejecutando y si los usuarios del servicio siempre formarán parte del mismo dominio de Windows en el que el servicio se está ejecutando. Puede crear con facilidad grupos de Windows que hayan especificado niveles de acceso (como ninguno, de solo lectura o lectura y escritura).  
  
 Para obtener más información sobre el uso del atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md). Para obtener más información acerca de la identidad, consulte [identidad de servicio y autenticación](service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>Proveedor de pertenencia a ASP.NET  

 Una característica de ASP.NET es el proveedor de pertenencia. Aunque el proveedor de pertenencia no es técnicamente un mecanismo de control de acceso, permite controlar el acceso al servicio limitando el conjunto de posibles identidades que pueden tener acceso al punto de conexión del servicio. La característica de pertenencia incluye una base de datos que se puede rellenar con combinaciones de nombre de usuario/contraseña que permitan a los usuarios de un sitio Web establecer cuentas en el sitio. Para tener acceso a un servicio que utiliza el proveedor de pertenencia, un usuario debe iniciar sesión con su nombre de usuario y contraseña.  
  
> [!NOTE]
> En primer lugar, debe rellenar la base de datos mediante la característica ASP.NET antes de que un servicio WCF pueda usarla con fines de autorización.  
  
 También puede usar la característica de pertenencia si ya tiene una base de datos de pertenencia de un sitio web de ASP.NET existente y desea permitir que los mismos usuarios utilicen el servicio, autorizado con los mismos nombres de usuario y contraseñas.  
  
 Para obtener más información sobre el uso de la característica de pertenencia en un servicio WCF, vea [Cómo: usar el proveedor de pertenencia a ASP.net](how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>Proveedor de roles ASP.NET  

 Otra característica de ASP.NET es la capacidad de administrar la autorización mediante roles. El proveedor de roles ASP.NET permite a un desarrollador crear roles para los usuarios y asignar cada usuario a un rol o a roles. Al igual que con el proveedor de pertenencia, los roles y las asignaciones se almacenan en una base de datos y se pueden rellenar con las herramientas proporcionadas por una implementación determinada del proveedor de roles ASP.NET. Al igual que con la característica de pertenencia, los desarrolladores de WCF pueden usar la información de la base de datos para autorizar a los usuarios del servicio por roles. Por ejemplo, pueden utilizar el proveedor de funciones en combinación con el mecanismo de control de acceso `PrincipalPermissionAttribute` descrito anteriormente.  
  
 También puede usar el proveedor de roles ASP.NET si tiene una base de datos de proveedor de roles ASP.NET existente y desea usar el mismo conjunto de reglas y asignaciones de usuarios en el servicio WCF.  
  
 Para obtener más información sobre el uso de la característica de proveedor de roles, vea [Cómo: usar el proveedor de roles ASP.net con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Administrador de autorización  

 Otra característica combina el administrador de autorización (AzMan) con el proveedor de funciones ASP.NET para autorizar a los clientes. Cuando ASP.NET hospeda un servicio Web, AzMan se puede integrar en la aplicación para que la autorización para el servicio se realice a través de AzMan. El administrador de roles de ASP.NET proporciona una API que permite administrar roles de aplicación, agregar y quitar usuarios de roles, y comprobar la pertenencia a roles, pero no permite consultar si un usuario está autorizado para realizar una tarea o operación con nombre. AzMan le permite definir operaciones individuales y combinarlas en tareas. Con AZMan, además de las comprobaciones de la función, también puede comprobar si un usuario puede realizar una tarea. La asignación de funciones y la autorización de tareas se pueden configurar fuera de la aplicación o se pueden realizar mediante programación dentro de la aplicación. El complemento Microsoft Management Console (MMC) de administración de AzMan permite a los administradores cambiar las tareas que una función puede realizar en tiempo de ejecución y administrar la pertenencia de funciones de cada usuario.  
  
 También puede usar AzMan y el proveedor de roles ASP.NET si ya tiene acceso a una instalación existente de AzMan y desea autorizar a los usuarios del servicio mediante las características de la combinación de proveedor de roles y AzMan.  
  
 Para obtener más información acerca de AzMan y el proveedor de roles ASP.NET, consulte [Cómo: usar el administrador de autorización (AzMan) con ASP.NET 2,0](/previous-versions/msp-n-p/ff649313(v=pandp.10)). Para obtener más información sobre el uso de AzMan y el proveedor de roles para los servicios WCF, consulte [Cómo: usar el proveedor de funciones del administrador de autorización de ASP.net con un servicio](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Modelo de identidad  

 El modelo de identidad es un conjunto de API que le permiten administrar demandas y directivas para autorizar a los clientes. Con el modelo de identidad, puede examinar cada demanda contenida en credenciales que el llamador utiliza para autenticarse a sí mismo para el servicio, comparar las demandas con el conjunto de directivas para el servicio y conceder o denegar acceso basándose en la comparación.  
  
 Utilice el modelo de identidad si necesita un control preciso y la capacidad de establecer criterios concretos antes de conceder el acceso. Por ejemplo, al utilizar <xref:System.Security.Permissions.PrincipalPermissionAttribute>, el criterio simplemente es que la identidad del usuario se pueda autenticar y pertenezca a una función concreta. En cambio, utilizando el modelo de identidad, puede crear una directiva que establezca que el usuario debe ser mayor de 18 años y poseer una licencia de conducir válida antes de que se le permita ver un documento.  
  
 Un ejemplo donde puede beneficiarse del control de acceso basado en notificaciones del modelo de identidad es al usar credenciales de federación en el escenario de token emitido. Para obtener más información sobre la Federación y los tokens emitidos, vea [Federación y tokens emitidos](federation-and-issued-tokens.md).  
  
 Para obtener más información sobre el modelo de identidad, consulte [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Procedimiento para usar el proveedor de roles ASP.NET con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)
- [Delegación y suplantación](delegation-and-impersonation-with-wcf.md)
