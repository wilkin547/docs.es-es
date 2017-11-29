---
title: "Solución de problemas: Ganadas de aplicación de servicio &#39; instalación t"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="4531d-102">Solución de problemas: Ganadas de aplicación de servicio &#39; instalación t</span><span class="sxs-lookup"><span data-stu-id="4531d-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="4531d-103">Si la aplicación de servicio no se instala correctamente, compruebe para asegurarse de que el <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> propiedad para la clase de servicio se establece en el mismo valor tal y como se muestra en el instalador para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="4531d-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="4531d-104">El valor debe ser el mismo en ambas instancias para el servicio instalar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4531d-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4531d-105">También puede buscar en los registros de instalación para obtener los comentarios en el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="4531d-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="4531d-106">También debe comprobar para determinar si tiene otro servicio con el mismo nombre ya instalado.</span><span class="sxs-lookup"><span data-stu-id="4531d-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="4531d-107">Nombres de servicio deben ser únicos para la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="4531d-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4531d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4531d-108">See Also</span></span>  
 [<span data-ttu-id="4531d-109">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="4531d-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
