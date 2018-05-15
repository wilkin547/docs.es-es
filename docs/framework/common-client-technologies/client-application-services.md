---
title: Servicios de aplicación cliente
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9532594f5f243faed28229388b9a6d597be57a7d
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="client-application-services"></a><span data-ttu-id="ae3fb-102">Servicios de aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="ae3fb-102">Client Application Services</span></span>
<span data-ttu-id="ae3fb-103">Los servicios de aplicaciones cliente facilitan la creación de aplicaciones basadas en Windows que usan el inicio de sesión, los roles y los servicios de aplicación de perfiles de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] incluidos en las extensiones de Microsoft ASP.NET 2.0 AJAX.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-103">Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions.</span></span> <span data-ttu-id="ae3fb-104">Estos servicios permiten que varias aplicaciones web y basadas en Windows compartan la información del usuario y la funcionalidad de administración de usuarios desde un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-104">These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server.</span></span> <span data-ttu-id="ae3fb-105">Por ejemplo, puede usar estos servicios para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae3fb-105">For example, you can use these services to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ae3fb-106">Autenticar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-106">Authenticate a user.</span></span> <span data-ttu-id="ae3fb-107">Puede usar el servicio de autenticación para comprobar la identidad de un usuario.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-107">You can use the authentication service to verify a user's identity.</span></span>  
  
-   <span data-ttu-id="ae3fb-108">Determinar el rol o roles de un usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-108">Determine the role or roles of an authenticated user.</span></span> <span data-ttu-id="ae3fb-109">Puede usar el servicio de roles para cambiar la interfaz de usuario de la aplicación, según el rol del usuario.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-109">You can use the roles service to change the user interface of your application depending on the user's role.</span></span> <span data-ttu-id="ae3fb-110">Por ejemplo, puede proporcionar características adicionales para los usuarios que tienen un rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-110">For example, you can provide additional features for users who are in an administrator role.</span></span>  
  
-   <span data-ttu-id="ae3fb-111">Almacenar y acceder a la configuración de la aplicación por usuario ubicada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-111">Store and access per-user application settings located on the server.</span></span> <span data-ttu-id="ae3fb-112">Puede usar el servicio de configuración web (también conocido como servicio de perfil) para compartir la configuración entre varias aplicaciones y ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-112">You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.</span></span>  
  
 <span data-ttu-id="ae3fb-113">Los servicios de aplicaciones cliente aprovechan el modelo de extensibilidad de los servicios web a través de proveedores de servicios cliente que se pueden especificar en los archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-113">Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files.</span></span> <span data-ttu-id="ae3fb-114">Estos proveedores de servicios incluyen la funcionalidad sin conexión que usa una caché local para la autenticación, los roles y los datos de configuración cuando no hay disponible una conexión de red.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-114">These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.</span></span>  
  
 <span data-ttu-id="ae3fb-115">Para más información sobre los servicios de la aplicación de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], consulte [Información general sobre los servicios de aplicación ASP.NET](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span><span class="sxs-lookup"><span data-stu-id="ae3fb-115">For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae3fb-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ae3fb-116">In This Section</span></span>  
 [<span data-ttu-id="ae3fb-117">Información general sobre los servicios de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="ae3fb-117">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 <span data-ttu-id="ae3fb-118">Describe las características disponibles a través de los proveedores de servicios de aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-118">Describes the features available through the client application service providers.</span></span>  
  
 [<span data-ttu-id="ae3fb-119">Cómo: Configurar servicios de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="ae3fb-119">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 <span data-ttu-id="ae3fb-120">Describe cómo usar el diseñador de proyectos de Visual Studio para habilitar y configurar servicios de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-120">Describes how to use the Visual Studio project designer to enable and configuration application services.</span></span> <span data-ttu-id="ae3fb-121">También describe los cambios correspondientes en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-121">Also describes the corresponding changes to your App.config file.</span></span>  
  
 [<span data-ttu-id="ae3fb-122">Cómo: Implementar el inicio de sesión de usuarios con servicios de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="ae3fb-122">How to: Implement User Login with Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 <span data-ttu-id="ae3fb-123">Describe cómo validar un usuario cuando la aplicación está configurada para usar un proveedor de servicios de autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-123">Describes how to validate a user when your application is configured to use a client authentication service provider.</span></span>  
  
 [<span data-ttu-id="ae3fb-124">Tutorial: Usar servicios de aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="ae3fb-124">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 <span data-ttu-id="ae3fb-125">Describe cómo combinar todas las características de servicios de aplicaciones cliente en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-125">Describes how to combine all client application services features in a single application.</span></span> <span data-ttu-id="ae3fb-126">Este tutorial proporciona instrucciones completas.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-126">This walkthrough provides end-to-end guidance.</span></span> <span data-ttu-id="ae3fb-127">Por ejemplo, incluye instrucciones sobre cómo crear una aplicación de servicio web de ASP.NET que se puede usar para probar los servicios de aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="ae3fb-127">For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ae3fb-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="ae3fb-128">Reference</span></span>  
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
  
## <a name="see-also"></a><span data-ttu-id="ae3fb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae3fb-129">See Also</span></span>  
 [<span data-ttu-id="ae3fb-130">Información general sobre los servicios de aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ae3fb-130">ASP.NET Application Services Overview</span></span>](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [<span data-ttu-id="ae3fb-131">Utilizar la autenticación de formularios con AJAX en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ae3fb-131">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [<span data-ttu-id="ae3fb-132">Usar información de funciones con AJAX en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ae3fb-132">Using Roles Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [<span data-ttu-id="ae3fb-133">Usar información de perfiles con AJAX en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ae3fb-133">Using Profile Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [<span data-ttu-id="ae3fb-134">Autenticación de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ae3fb-134">ASP.NET Authentication</span></span>](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 <span data-ttu-id="ae3fb-135">[Administrar autorizaciones con funciones](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span><span class="sxs-lookup"><span data-stu-id="ae3fb-135">[Managing Authorization Using Roles](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span></span>  
 [<span data-ttu-id="ae3fb-136">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae3fb-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)
