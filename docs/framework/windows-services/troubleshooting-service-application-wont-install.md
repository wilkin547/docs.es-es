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
# <a name="troubleshooting-service-application-won39t-install"></a>Solución del problema: la aplicación de servicio no se instala
Si la aplicación de servicio no se instala correctamente, compruebe que la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para la clase de servicio está configurada con el mismo valor que se muestra en el instalador para ese servicio. El valor debe ser el mismo en ambos casos para que el servicio se instale correctamente.  
  
> [!NOTE]
>  También puede consultar los registros de instalación para obtener comentarios sobre el proceso de instalación.  
  
 También debe comprobar si tiene otro servicio con el mismo nombre ya instalado. Los nombres de los servicios deben ser únicos para que la instalación se realice correctamente.  
  
## <a name="see-also"></a>Vea también
- [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
