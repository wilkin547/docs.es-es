---
title: Servicios de aplicación cliente
ms.date: 03/30/2017
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
ms.openlocfilehash: d58510240593f73ff761aa669035f28598006c10
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522005"
---
# <a name="client-application-services"></a>Servicios de aplicación cliente
Los servicios de aplicaciones cliente facilitan la creación de aplicaciones basadas en Windows que usan el inicio de sesión, los roles y los servicios de aplicación de perfiles de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] incluidos en las extensiones de Microsoft ASP.NET 2.0 AJAX. Estos servicios permiten que varias aplicaciones web y basadas en Windows compartan la información del usuario y la funcionalidad de administración de usuarios desde un solo servidor. Por ejemplo, puede usar estos servicios para realizar las tareas siguientes:  
  
-   Autenticar a un usuario. Puede usar el servicio de autenticación para comprobar la identidad de un usuario.  
  
-   Determinar el rol o roles de un usuario autenticado. Puede usar el servicio de roles para cambiar la interfaz de usuario de la aplicación, según el rol del usuario. Por ejemplo, puede proporcionar características adicionales para los usuarios que tienen un rol de administrador.  
  
-   Almacenar y acceder a la configuración de la aplicación por usuario ubicada en el servidor. Puede usar el servicio de configuración web (también conocido como servicio de perfil) para compartir la configuración entre varias aplicaciones y ubicaciones.  
  
 Los servicios de aplicaciones cliente aprovechan el modelo de extensibilidad de los servicios web a través de proveedores de servicios cliente que se pueden especificar en los archivos de configuración de la aplicación. Estos proveedores de servicios incluyen la funcionalidad sin conexión que usa una caché local para la autenticación, los roles y los datos de configuración cuando no hay disponible una conexión de red.  
  
 Para más información sobre los servicios de la aplicación de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], consulte [Información general sobre los servicios de aplicación ASP.NET](https://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre los servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Describe las características disponibles a través de los proveedores de servicios de aplicaciones cliente.  
  
 [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Describe cómo usar el diseñador de proyectos de Visual Studio para habilitar y configurar servicios de aplicaciones. También describe los cambios correspondientes en el archivo App.config.  
  
 [Cómo: Implementar el inicio de sesión de usuarios con servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Describe cómo validar un usuario cuando la aplicación está configurada para usar un proveedor de servicios de autenticación de cliente.  
  
 [Tutorial: Usar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Describe cómo combinar todas las características de servicios de aplicaciones cliente en una sola aplicación. Este tutorial proporciona instrucciones completas. Por ejemplo, incluye instrucciones sobre cómo crear una aplicación de servicio web de ASP.NET que se puede usar para probar los servicios de aplicaciones cliente.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre los servicios de aplicación ASP.NET](https://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [Utilizar la autenticación de formularios con AJAX en ASP.NET](https://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [Usar información de funciones con AJAX en ASP.NET](https://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [Usar información de perfiles con AJAX en ASP.NET](https://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [Autenticación de ASP.NET](https://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 [Administrar autorizaciones con funciones](https://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)    
 [Introducción a la configuración de la aplicación](../../../docs/framework/winforms/advanced/application-settings-overview.md)
