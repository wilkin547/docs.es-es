---
title: 'Solución de problemas: Servicio aplicación ganadas&#39;Install t'
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
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>Solución de problemas: Servicio aplicación ganadas&#39;Install t
Si la aplicación de servicio no se instala correctamente, compruebe para asegurarse de que el <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> propiedad para la clase de servicio se establece en el mismo valor tal y como se muestra en el instalador para ese servicio. El valor debe ser el mismo en ambas instancias para el servicio instalar correctamente.  
  
> [!NOTE]
>  También puede buscar en los registros de instalación para obtener los comentarios en el proceso de instalación.  
  
 También debe comprobar para determinar si tiene otro servicio con el mismo nombre ya instalado. Nombres de servicio deben ser únicos para la instalación se realice correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
