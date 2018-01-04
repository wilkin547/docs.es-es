---
title: "Utilización de las herramientas de desarrollo de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d253f38fab21496dd305cc67e7b6e84846579f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="88d51-102">Utilización de las herramientas de desarrollo de WCF</span><span class="sxs-lookup"><span data-stu-id="88d51-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="88d51-103">Esta sección se describe la [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] herramientas de desarrollo que pueden ayudarle a desarrollar su [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]servicio.</span><span class="sxs-lookup"><span data-stu-id="88d51-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="88d51-104">Puede usar el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] plantillas como base para generar rápidamente su propio servicio y, a continuación, usar [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automático del servicio y [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para depurar y probar el servicio de cliente de prueba.</span><span class="sxs-lookup"><span data-stu-id="88d51-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="88d51-105">Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de adaptarse a un modelo de hospedaje en una fase temprana.</span><span class="sxs-lookup"><span data-stu-id="88d51-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="88d51-106">Herramientas de desarrollador de WCF</span><span class="sxs-lookup"><span data-stu-id="88d51-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="88d51-107">Plantillas de Visual Studio para WCF</span><span class="sxs-lookup"><span data-stu-id="88d51-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="88d51-108">Puede usar predefinido [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] plantillas de proyecto y elemento de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para generar rápidamente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicios y aplicaciones que lo rodea.</span><span class="sxs-lookup"><span data-stu-id="88d51-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="88d51-109">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="88d51-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="88d51-110">El host automático de servicio (WcfSvcHost.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] permite iniciar el depurador (F5) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para hospedar y probar automáticamente un servicio implementado.</span><span class="sxs-lookup"><span data-stu-id="88d51-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="88d51-111">Después, puede probar el servicio utilizando el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe), o su propio cliente, para buscar y corregir cualquier error potencial.</span><span class="sxs-lookup"><span data-stu-id="88d51-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="88d51-112">Cliente de prueba de WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="88d51-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="88d51-113">El cliente de prueba (WcfTestClient.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una herramienta GUI que permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio, y ver la respuesta que devuelve el servicio.</span><span class="sxs-lookup"><span data-stu-id="88d51-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="88d51-114">Proporciona un servicio de prueba sin problemas cuando se combina con el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88d51-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="88d51-115">Generación de clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="88d51-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="88d51-116">Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="88d51-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="88d51-117">Las clases definidas en los datos se convertirán en tipos de código.</span><span class="sxs-lookup"><span data-stu-id="88d51-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="88d51-118">Utilización de las herramientas sin el privilegio de administrador</span><span class="sxs-lookup"><span data-stu-id="88d51-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="88d51-119">Para permitir que los usuarios sin el privilegio de administrador desarrollen servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se crea una ACL (Lista de control de acceso) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88d51-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="88d51-120">La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo.</span><span class="sxs-lookup"><span data-stu-id="88d51-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="88d51-121">Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88d51-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="88d51-122">También permite a los usuarios utilizar el host automático de servicio (wcfSvcHost.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sin concederles los privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="88d51-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="88d51-123">Puede modificar el acceso mediante la herramienta Netsh.exe de [!INCLUDE[wv](../../../includes/wv-md.md)] con la cuenta elevada de administrador.</span><span class="sxs-lookup"><span data-stu-id="88d51-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="88d51-124">En el siguiente ejemplo se muestra el uso de Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="88d51-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="88d51-125">Netsh.exe, consulte [cómo usar la herramienta Netsh.exe y los modificadores de línea de comandos](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="88d51-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d51-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="88d51-126">See Also</span></span>  
 [<span data-ttu-id="88d51-127">Plantillas de Visual Studio para WCF</span><span class="sxs-lookup"><span data-stu-id="88d51-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="88d51-128">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="88d51-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="88d51-129">Cliente de prueba de WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="88d51-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
