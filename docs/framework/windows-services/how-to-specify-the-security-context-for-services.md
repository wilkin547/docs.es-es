---
title: Procedimiento para especificar el contexto de seguridad de los servicios
description: Especifique el contexto de seguridad de los servicios. Los servicios que se ejecutan en el contexto predeterminado de la cuenta del sistema tienen derechos de acceso a los recursos del sistema diferentes a los del usuario que ha iniciado sesión.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
ms.openlocfilehash: dcf0680f1bcb0f0e927bdb37ea56f7b3025be09b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270542"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="de4f8-104">Procedimiento para especificar el contexto de seguridad de los servicios</span><span class="sxs-lookup"><span data-stu-id="de4f8-104">How to: Specify the Security Context for Services</span></span>

<span data-ttu-id="de4f8-105">De forma predeterminada, los servicios se ejecutan en un contexto de seguridad diferente al del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="de4f8-105">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="de4f8-106">Los servicios se ejecutan en el contexto de la cuenta del sistema predeterminado, llamada `LocalSystem`, que les da diferentes privilegios de acceso a los recursos del sistema que el usuario.</span><span class="sxs-lookup"><span data-stu-id="de4f8-106">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="de4f8-107">Puede cambiar este comportamiento para especificar una cuenta de usuario diferente bajo la cual se debe ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="de4f8-107">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="de4f8-108">Se establece el contexto de seguridad mediante la manipulación de la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> para el proceso dentro del cual se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="de4f8-108">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="de4f8-109">Esta propiedad le permite establecer el servicio en uno de los cuatro tipos de cuenta:</span><span class="sxs-lookup"><span data-stu-id="de4f8-109">This property allows you to set the service to one of four account types:</span></span>  
  
- <span data-ttu-id="de4f8-110">`User`, lo que hace que el sistema solicite un nombre de usuario y una contraseña válidos cuando el servicio está instalado y se ejecuta en el contexto de una cuenta especificada por un único usuario en la red;</span><span class="sxs-lookup"><span data-stu-id="de4f8-110">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
- <span data-ttu-id="de4f8-111">`LocalService`, que se ejecuta en el contexto de una cuenta que actúa como usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto;</span><span class="sxs-lookup"><span data-stu-id="de4f8-111">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
- <span data-ttu-id="de4f8-112">`LocalSystem`, que se ejecuta en el contexto de una cuenta que proporciona amplios privilegios locales y presenta las credenciales del equipo a cualquier servidor remoto;</span><span class="sxs-lookup"><span data-stu-id="de4f8-112">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
- <span data-ttu-id="de4f8-113">Para otras tareas, considere la posibilidad de usar la cuenta `NetworkService`, que actúa como un usuario sin privilegios en el equipo local y presenta credenciales del equipo a cualquier servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="de4f8-113">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="de4f8-114">Para obtener más información, vea la enumeración <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="de4f8-114">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="de4f8-115">Para especificar el contexto de seguridad de un servicio</span><span class="sxs-lookup"><span data-stu-id="de4f8-115">To specify the security context for a service</span></span>  
  
1. <span data-ttu-id="de4f8-116">Después de crear su servicio, agregue los instaladores necesarios para ello.</span><span class="sxs-lookup"><span data-stu-id="de4f8-116">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="de4f8-117">Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="de4f8-117">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="de4f8-118">En el diseñador, acceda a la clase `ProjectInstaller` y haga clic en el instalador del proceso de servicio para el servicio con el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="de4f8-118">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="de4f8-119">Para cada aplicación de servicio, hay al menos dos componentes de instalación en la clase `ProjectInstaller`: uno que instala los procesos para todos los servicios del proyecto y un instalador para cada servicio que contiene la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de4f8-119">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="de4f8-120">En este caso, desea seleccionar <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="de4f8-120">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3. <span data-ttu-id="de4f8-121">En la ventana **Propiedades**, establezca <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> al valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="de4f8-121">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4f8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4f8-122">See also</span></span>

- [<span data-ttu-id="de4f8-123">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="de4f8-123">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="de4f8-124">Cómo: Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="de4f8-124">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="de4f8-125">Cómo: Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="de4f8-125">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
