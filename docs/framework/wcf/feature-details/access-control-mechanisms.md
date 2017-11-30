---
title: Mecanismos de control de acceso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f43de08a81afcf9ff6ab29b862f22c2935eca55f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-control-mechanisms"></a>Mecanismos de control de acceso
Puede controlar el acceso de varias maneras con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Este tema aborda brevemente los diversos mecanismos y proporciona sugerencias sobre cuándo utilizar cada uno; está destinado a ayudarle a seleccionar el mecanismo correcto a utilizar. Las tecnologías de acceso están listadas por orden de complejidad. La más simple es <xref:System.Security.Permissions.PrincipalPermissionAttribute>; la más compleja es el modelo de identidad.  
  
 Además de estos mecanismos, suplantación y delegación con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se explica en [delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> se utiliza para restringir el acceso a un método de servicio. Cuando el atributo se aplica a un método, se puede utilizar para exigir la identidad de un llamador concreto o la pertenencia a un grupo de Windows o función [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Si el cliente se autentica utilizando un certificado X.509, se le proporciona una identidad primaria que está compuesta del nombre de sujeto más la huella digital del certificado.  
  
 Utilice <xref:System.Security.Permissions.PrincipalPermissionAttribute> para controlar el acceso a los recursos en el equipo en el que el servicio se está ejecutando y si los usuarios del servicio siempre formarán parte del mismo dominio de Windows en el que el servicio se está ejecutando. Puede crear con facilidad grupos de Windows que hayan especificado niveles de acceso (como ninguno, de solo lectura o lectura y escritura).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mediante el atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]identidad, vea [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>Proveedor de pertenencia a ASP.NET  
 Una característica de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es el proveedor de pertenencia. Aunque el proveedor de pertenencia no es técnicamente un mecanismo de control de acceso, permite controlar el acceso al servicio limitando el conjunto de posibles identidades que pueden tener acceso al extremo del servicio. La característica de pertenencia incluye una base de datos que se puede rellenar con combinaciones de nombre de usuario/contraseña que permitan a los usuarios de un sitio Web establecer cuentas en el sitio. Para tener acceso a un servicio que utiliza el proveedor de pertenencia, un usuario debe registrarse en con su nombre de usuario y contraseña.  
  
> [!NOTE]
>  Primero debe rellenar la base de datos utilizando la característica [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] antes de que un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueda utilizarla para los propósitos de la autorización.  
  
 También puede utilizar la característica de pertenencia si ya tiene una base de datos de pertenencias de un sitio Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente y desea permitir a los mismos usuarios que utilicen su servicio, autorizándolos con los mismos nombres de usuario y contraseñas.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mediante la característica de pertenencia en una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio, vea [Cómo: usar el proveedor de pertenencia a ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>Proveedor de roles ASP.NET  
 Otra característica de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es la capacidad de administrar la autorización mediante las funciones. El proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] permite a un programador crear las funciones para los usuarios y asignar a cada usuario una función o funciones. Como con el proveedor de pertenencia, las funciones y asignaciones están almacenados en una base de datos y se pueden rellenar utilizando las herramientas proporcionadas por una implementación determinada del proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Como con la característica de pertenencia, los programadores [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden utilizar la información en la base de datos para autorizar a los usuarios del servicio mediante funciones. Por ejemplo, pueden utilizar el proveedor de funciones en combinación con el mecanismo de control de acceso `PrincipalPermissionAttribute` descrito anteriormente.  
  
 También puede utilizar el proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] si tiene una base de datos de proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente y desea utilizar el mismo conjunto de reglas y asignaciones de usuario en su servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]con la característica de proveedor de roles, consulte [Cómo: utilizar el proveedor de funciones de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Administrador de autorización  
 Otra característica combina el Administrador de autorización (AzMan) con el proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] para autorizar a los clientes. Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda un servicio web, AzMan se puede integrar en la aplicación de modo que la autorización para el servicio se realice mediante AzMan. El administrador de roles de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proporciona una API que permite administrar roles de aplicación, agregar y quitar usuarios de roles, y comprobar la pertenencia a roles, pero no permite consultar si un usuario está autorizado para realizar una tarea o una operación con nombre. AzMan le permite definir operaciones individuales y combinarlas en tareas. Con AZMan, además de las comprobaciones de la función, también puede comprobar si un usuario puede realizar una tarea. La asignación de funciones y la autorización de tareas se pueden configurar fuera de la aplicación o se pueden realizar mediante programación dentro de la aplicación. El complemento Microsoft Management Console (MMC) de administración de AzMan permite a los administradores cambiar las tareas que una función puede realizar en tiempo de ejecución y administrar la pertenencia de funciones de cada usuario.  
  
 También puede utilizar AzMan y el proveedor de roles de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] si ya tiene el acceso a una instalación AzMan existente y desea autorizar su servicio a los usuarios utilizando las características de la combinación de AzMan/proveedor de roles.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]AzMan y el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles, consulte [How To: Use el Administrador de autorización (AzMan) con ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=88951). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]con AzMan y el proveedor de funciones para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicios, vea [Cómo: utilizar el proveedor de funciones de administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Modelo de identidad  
 El modelo de identidad es un conjunto de API que le permiten administrar demandas y directivas para autorizar a los clientes. Con el modelo de identidad, puede examinar cada demanda contenida en credenciales que el llamador utiliza para autenticarse a sí mismo para el servicio, comparar las demandas con el conjunto de directivas para el servicio y conceder o denegar acceso basándose en la comparación.  
  
 Utilice el modelo de identidad si necesita un control preciso y la capacidad de establecer criterios concretos antes de conceder el acceso. Por ejemplo, al utilizar <xref:System.Security.Permissions.PrincipalPermissionAttribute>, el criterio simplemente es que la identidad del usuario se pueda autenticar y pertenezca a una función concreta. En cambio, utilizando el modelo de identidad, puede crear una directiva que establezca que el usuario debe ser mayor de 18 años y poseer una licencia de conducir válida antes de que se le permita ver un documento.  
  
 Un ejemplo donde puede beneficiarse del control de acceso basado en notificaciones del modelo de identidad es al usar credenciales de federación en el escenario de token emitido. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]federación y tokens emitidos, vea [federación y Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]el modelo de identidad, vea [Administrar notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [Cómo: utilizar el proveedor de funciones de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Cómo: utilizar el proveedor de funciones de administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
