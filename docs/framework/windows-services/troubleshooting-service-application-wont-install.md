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
# <a name="troubleshooting-service-application-won39t-install"></a>Solución de problemas: Ganadas de aplicación de servicio &#39; instalación t
Si la aplicación de servicio no se instala correctamente, compruebe para asegurarse de que el <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> propiedad para la clase de servicio se establece en el mismo valor tal y como se muestra en el instalador para ese servicio. El valor debe ser el mismo en ambas instancias para el servicio instalar correctamente.  
  
> [!NOTE]
>  También puede buscar en los registros de instalación para obtener los comentarios en el proceso de instalación.  
  
 También debe comprobar para determinar si tiene otro servicio con el mismo nombre ya instalado. Nombres de servicio deben ser únicos para la instalación se realice correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
