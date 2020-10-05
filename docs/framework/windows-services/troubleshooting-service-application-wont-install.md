---
title: 'Solución del problema: la aplicación de servicio no se instala'
description: Siga el proceso de solución de problemas si la aplicación de servicio no se instala. Asegúrese de que la propiedad ServiceName de la clase de servicio está establecida correctamente.
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
ms.openlocfilehash: d606adc7fddeb9f7e76a6974699c2455eda084b2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608886"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="1839b-104">Solución del problema: la aplicación de servicio no se instala</span><span class="sxs-lookup"><span data-stu-id="1839b-104">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="1839b-105">Si la aplicación de servicio no se instala correctamente, compruebe que la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para la clase de servicio está configurada con el mismo valor que se muestra en el instalador para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="1839b-105">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="1839b-106">El valor debe ser el mismo en ambos casos para que el servicio se instale correctamente.</span><span class="sxs-lookup"><span data-stu-id="1839b-106">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1839b-107">También puede consultar los registros de instalación para obtener comentarios sobre el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="1839b-107">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="1839b-108">También debe comprobar si tiene otro servicio con el mismo nombre ya instalado.</span><span class="sxs-lookup"><span data-stu-id="1839b-108">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="1839b-109">Los nombres de los servicios deben ser únicos para que la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="1839b-109">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1839b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1839b-110">See also</span></span>

- [<span data-ttu-id="1839b-111">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="1839b-111">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
