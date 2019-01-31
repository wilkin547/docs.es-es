---
title: 'Solución del problema: la aplicación de servicio no se instala'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: 998c7a3f5ca405b3bd66b877d027126f6c76cc15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494423"
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="31692-102">Solución del problema: la aplicación de servicio no se instala</span><span class="sxs-lookup"><span data-stu-id="31692-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="31692-103">Si la aplicación de servicio no se instala correctamente, compruebe que la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para la clase de servicio está configurada con el mismo valor que se muestra en el instalador para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="31692-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="31692-104">El valor debe ser el mismo en ambos casos para que el servicio se instale correctamente.</span><span class="sxs-lookup"><span data-stu-id="31692-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31692-105">También puede consultar los registros de instalación para obtener comentarios sobre el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="31692-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="31692-106">También debe comprobar si tiene otro servicio con el mismo nombre ya instalado.</span><span class="sxs-lookup"><span data-stu-id="31692-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="31692-107">Los nombres de los servicios deben ser únicos para que la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="31692-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31692-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="31692-108">See also</span></span>
- [<span data-ttu-id="31692-109">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="31692-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
