---
title: "Servicios de aplicaci&#243;n cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "configuración de la aplicación, servicios de aplicación cliente"
  - "servicios ASP.NET, servicios de aplicación cliente"
  - "autenticación [ASP.NET], servicios de aplicación cliente"
  - "servicios de aplicación cliente"
  - "servicios de aplicación cliente, acerca de los servicios de aplicación cliente"
  - "aplicaciones cliente, servicios ASP.NET"
  - "credenciales [.NET Framework]"
  - "inicios de sesión [servicios de aplicación cliente]"
  - "perfiles [ASP.NET], servicios de aplicación cliente"
  - "seguridad basada en roles [.NET Framework], servicios de aplicación cliente"
  - "roles [.NET Framework], servicios de aplicación cliente"
  - "compartir información y funcionalidad [servicios de aplicación cliente]"
  - "configuración web [servicios de aplicación cliente]"
  - "aplicaciones basadas en Windows, servicios de aplicación cliente"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Servicios de aplicaci&#243;n cliente
Los servicios de aplicaciones cliente facilitan la creación de aplicaciones basadas en Windows que usan el inicio de sesión, los roles y los servicios de aplicación de perfiles de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] incluidos en las extensiones de Microsoft ASP.NET 2.0 AJAX.  Estos servicios permiten que varias aplicaciones web y basadas en Windows compartan la información del usuario y la funcionalidad de administración de usuarios desde un solo servidor.  Por ejemplo, puede usar estos servicios para realizar las tareas siguientes:  
  
-   Autenticar a un usuario.  Puede usar el servicio de autenticación para comprobar la identidad de un usuario.  
  
-   Determinar el rol o roles de un usuario autenticado.  Puede usar el servicio de roles para cambiar la interfaz de usuario de la aplicación, según el rol del usuario.  Por ejemplo, puede proporcionar características adicionales para los usuarios que tienen un rol de administrador.  
  
-   Almacenar y acceder a la configuración de la aplicación por usuario ubicada en el servidor.  Puede usar el servicio de configuración web \(también conocido como servicio de perfil\) para compartir la configuración entre varias aplicaciones y ubicaciones.  
  
 Los servicios de aplicaciones cliente aprovechan el modelo de extensibilidad de los servicios web a través de proveedores de servicios cliente que se pueden especificar en los archivos de configuración de la aplicación.  Estos proveedores de servicios incluyen la funcionalidad sin conexión que usa una caché local para la autenticación, los roles y los datos de configuración cuando no hay disponible una conexión de red.  
  
 Para obtener más información sobre los servicios de la aplicación de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], vea [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md).  
  
## En esta sección  
 [Información general sobre los servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Describe las características disponibles a través de los proveedores de servicios de aplicaciones cliente.  
  
 [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Describe cómo usar el diseñador de proyectos de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para habilitar y configurar servicios de aplicaciones.  También describe los cambios correspondientes en el archivo App.config.  
  
 [Cómo: Implementar el inicio de sesión de usuarios con servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Describe cómo validar un usuario cuando la aplicación está configurada para usar un proveedor de servicios de autenticación de cliente.  
  
 [Tutorial: Usar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Describe cómo combinar todas las características de servicios de aplicaciones cliente en una sola aplicación.  Este tutorial proporciona instrucciones completas.  Por ejemplo, incluye instrucciones sobre cómo crear una aplicación de servicio web de ASP.NET que se puede usar para probar los servicios de aplicaciones cliente.  
  
## Referencia  
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
  
## Vea también  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/es-es/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [Introducción a la configuración de la aplicación](../../../docs/framework/winforms/advanced/application-settings-overview.md)