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
ms.openlocfilehash: c45ab03ec4577d88953b0e43531082a46c29e8fd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053532"
---
# <a name="troubleshooting-service-application-wont-install"></a>Solución del problema: la aplicación de servicio no se instala
Si la aplicación de servicio no se instala correctamente, compruebe que la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para la clase de servicio está configurada con el mismo valor que se muestra en el instalador para ese servicio. El valor debe ser el mismo en ambos casos para que el servicio se instale correctamente.  
  
> [!NOTE]
> También puede consultar los registros de instalación para obtener comentarios sobre el proceso de instalación.  
  
 También debe comprobar si tiene otro servicio con el mismo nombre ya instalado. Los nombres de los servicios deben ser únicos para que la instalación se realice correctamente.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
