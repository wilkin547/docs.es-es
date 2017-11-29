---
title: "Cómo: Especificar el contexto de seguridad de los servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 50a9c6ff7f02cda4475aa5390181fa5d410af161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="d2bc8-102">Cómo: Especificar el contexto de seguridad de los servicios</span><span class="sxs-lookup"><span data-stu-id="d2bc8-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="d2bc8-103">De forma predeterminada, los servicios se ejecutan en un contexto de seguridad diferente que el usuario ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="d2bc8-104">Se ejecutan en el contexto de la cuenta de sistema de forma predeterminada, los servicios denominado `LocalSystem`, lo que les permitirá diferentes privilegios de acceso a recursos del sistema que el usuario.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="d2bc8-105">Puede cambiar este comportamiento para especificar una cuenta de usuario diferente bajo el que debe ejecutarse el servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="d2bc8-106">Para establecer el contexto de seguridad mediante la manipulación del <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> propiedad para el proceso en el que se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="d2bc8-107">Esta propiedad le permite establecer el servicio en uno de cuatro tipos de cuenta:</span><span class="sxs-lookup"><span data-stu-id="d2bc8-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="d2bc8-108">`User`, que hace que el sistema solicite un nombre de usuario válido y una contraseña cuando el servicio está instalado y se ejecuta en el contexto de una cuenta especificada por un único usuario de la red;</span><span class="sxs-lookup"><span data-stu-id="d2bc8-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="d2bc8-109">`LocalService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto;</span><span class="sxs-lookup"><span data-stu-id="d2bc8-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="d2bc8-110">`LocalSystem`, que se ejecuta en el contexto de una cuenta que proporciona amplios privilegios locales y presenta las credenciales del equipo a cualquier servidor remoto;</span><span class="sxs-lookup"><span data-stu-id="d2bc8-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="d2bc8-111">`NetworkService`, que se ejecuta en el contexto de una cuenta que actúa como un usuario sin privilegios en el equipo local y presenta las credenciales del equipo a cualquier servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="d2bc8-112">Para obtener más información, vea la enumeración <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="d2bc8-113">Para especificar el contexto de seguridad para un servicio</span><span class="sxs-lookup"><span data-stu-id="d2bc8-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="d2bc8-114">Después de crear el servicio, agregar a los instaladores necesarios para él.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="d2bc8-115">Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="d2bc8-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="d2bc8-116">En el diseñador, tener acceso a la `ProjectInstaller` clase y haga clic en el instalador de proceso de servicio para el servicio que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2bc8-117">Para cada aplicación de servicio, hay al menos dos componentes de instalación en la `ProjectInstaller` clase: uno que instala los procesos para todos los servicios en el proyecto y un instalador para cada servicio que contenga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="d2bc8-118">En este caso, desea seleccionar <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="d2bc8-119">En el **propiedades** ventana, establezca el <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="d2bc8-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bc8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2bc8-120">See Also</span></span>  
 [<span data-ttu-id="d2bc8-121">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="d2bc8-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="d2bc8-122">Cómo: agregar instaladores a la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="d2bc8-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="d2bc8-123">Cómo: crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="d2bc8-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
