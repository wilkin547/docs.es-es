---
title: Mecanismos de control de acceso
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: 1de6731591e524080ac4ae7d5b2ec2a25a27f301
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43777225"
---
# <a name="access-control-mechanisms"></a>Mecanismos de control de acceso
Puede controlar el acceso de varias maneras con Windows Communication Foundation (WCF). Este tema aborda brevemente los diversos mecanismos y proporciona sugerencias sobre cuándo utilizar cada uno; está destinado a ayudarle a seleccionar el mecanismo correcto a utilizar. Las tecnologías de acceso están listadas por orden de complejidad. La más simple es <xref:System.Security.Permissions.PrincipalPermissionAttribute>; la más compleja es el modelo de identidad.  
  
 Además de estos mecanismos, se explica en la suplantación y delegación con WCF [delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> se utiliza para restringir el acceso a un método de servicio. Cuando el atributo se aplica a un método, se puede utilizar para exigir la identidad de un llamador concreto o la pertenencia a un grupo de Windows o función [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Si el cliente se autentica utilizando un certificado X.509, se le proporciona una identidad primaria que está compuesta del nombre de sujeto más la huella digital del certificado.  
  
 Utilice <xref:System.Security.Permissions.PrincipalPermissionAttribute> para controlar el acceso a los recursos en el equipo en el que el servicio se está ejecutando y si los usuarios del servicio siempre formarán parte del mismo dominio de Windows en el que el servicio se está ejecutando. Puede crear con facilidad grupos de Windows que hayan especificado niveles de acceso (como ninguno, de solo lectura o lectura y escritura).  
  
 Para obtener más información sobre cómo utilizar el atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). Para obtener más información acerca de la identidad, vea [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>Proveedor de pertenencia a ASP.NET  
 Una característica de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es el proveedor de pertenencia. Aunque el proveedor de pertenencia no es técnicamente un mecanismo de control de acceso, permite controlar el acceso al servicio limitando el conjunto de posibles identidades que pueden tener acceso al punto de conexión del servicio. La característica de pertenencia incluye una base de datos que se puede rellenar con combinaciones de nombre de usuario/contraseña que permitan a los usuarios de un sitio Web establecer cuentas en el sitio. Para tener acceso a un servicio que utiliza el proveedor de pertenencia, un usuario debe registrarse en con su nombre de usuario y contraseña.  
  
> [!NOTE]
>  En primer lugar debe rellenar la base de datos mediante el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] características antes de que un servicio WCF puede usarse para fines de autorización.  
  
 También puede utilizar la característica de pertenencia si ya tiene una base de datos de pertenencias de un sitio Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente y desea permitir a los mismos usuarios que utilicen su servicio, autorizándolos con los mismos nombres de usuario y contraseñas.  
  
 Para obtener más información sobre cómo usar la característica de pertenencia en un servicio WCF, vea [Cómo: usar el proveedor de pertenencia a ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>Proveedor de roles ASP.NET  
 Otra característica de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es la capacidad de administrar la autorización mediante las funciones. El proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] permite a un programador crear las funciones para los usuarios y asignar a cada usuario una función o funciones. Como con el proveedor de pertenencia, las funciones y asignaciones están almacenados en una base de datos y se pueden rellenar utilizando las herramientas proporcionadas por una implementación determinada del proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Como con la característica de pertenencia, los desarrolladores de WCF pueden usar la información en la base de datos para autorizar a los usuarios del servicio de roles. Por ejemplo, pueden utilizar el proveedor de funciones en combinación con el mecanismo de control de acceso `PrincipalPermissionAttribute` descrito anteriormente.  
  
 También puede usar el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles si dispone de una [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] base de datos de proveedor de roles y desea volver a usar el mismo conjunto de reglas y las asignaciones de usuario en el servicio WCF.  
  
 Para obtener más información sobre cómo usar la característica de proveedor de roles, consulte [Cómo: utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Administrador de autorización  
 Otra característica combina el Administrador de autorización (AzMan) con el proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] para autorizar a los clientes. Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda un servicio web, AzMan se puede integrar en la aplicación de modo que la autorización para el servicio se realice mediante AzMan. El administrador de roles de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proporciona una API que permite administrar roles de aplicación, agregar y quitar usuarios de roles, y comprobar la pertenencia a roles, pero no permite consultar si un usuario está autorizado para realizar una tarea o una operación con nombre. AzMan le permite definir operaciones individuales y combinarlas en tareas. Con AZMan, además de las comprobaciones de la función, también puede comprobar si un usuario puede realizar una tarea. La asignación de funciones y la autorización de tareas se pueden configurar fuera de la aplicación o se pueden realizar mediante programación dentro de la aplicación. El complemento Microsoft Management Console (MMC) de administración de AzMan permite a los administradores cambiar las tareas que una función puede realizar en tiempo de ejecución y administrar la pertenencia de funciones de cada usuario.  
  
 También puede utilizar AzMan y el proveedor de roles de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] si ya tiene el acceso a una instalación AzMan existente y desea autorizar su servicio a los usuarios utilizando las características de la combinación de AzMan/proveedor de roles.  
  
 Para obtener más información acerca de AzMan y el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles, consulte [Cómo: usar el Administrador de autorización (AzMan) con ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=88951). Para obtener más información sobre el uso de AzMan y el proveedor de roles para los servicios WCF, vea [Cómo: utilizar el proveedor de roles de administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Modelo de identidad  
 El modelo de identidad es un conjunto de API que le permiten administrar demandas y directivas para autorizar a los clientes. Con el modelo de identidad, puede examinar cada demanda contenida en credenciales que el llamador utiliza para autenticarse a sí mismo para el servicio, comparar las demandas con el conjunto de directivas para el servicio y conceder o denegar acceso basándose en la comparación.  
  
 Utilice el modelo de identidad si necesita un control preciso y la capacidad de establecer criterios concretos antes de conceder el acceso. Por ejemplo, al utilizar <xref:System.Security.Permissions.PrincipalPermissionAttribute>, el criterio simplemente es que la identidad del usuario se pueda autenticar y pertenezca a una función concreta. En cambio, utilizando el modelo de identidad, puede crear una directiva que establezca que el usuario debe ser mayor de 18 años y poseer una licencia de conducir válida antes de que se le permita ver un documento.  
  
 Un ejemplo donde puede beneficiarse del control de acceso basado en notificaciones del modelo de identidad es al usar credenciales de federación en el escenario de token emitido. Para obtener más información acerca de la federación y tokens emitidos, vea [federación y Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Para obtener más información sobre el modelo de identidad, vea [Administrar notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [Uso del proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Uso del proveedor de funciones del administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
