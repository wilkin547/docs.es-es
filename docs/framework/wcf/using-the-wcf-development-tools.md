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
# <a name="using-the-wcf-development-tools"></a>Utilización de las herramientas de desarrollo de WCF
Esta sección se describe la [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] herramientas de desarrollo que pueden ayudarle a desarrollar su [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]servicio.  
  
 Puede usar el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] plantillas como base para generar rápidamente su propio servicio y, a continuación, usar [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automático del servicio y [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para depurar y probar el servicio de cliente de prueba. Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de adaptarse a un modelo de hospedaje en una fase temprana.  
  
## <a name="the-wcf-developer-tools"></a>Herramientas de desarrollador de WCF  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Puede usar predefinido [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] plantillas de proyecto y elemento de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para generar rápidamente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicios y aplicaciones que lo rodea.  
  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 El host automático de servicio (WcfSvcHost.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] permite iniciar el depurador (F5) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para hospedar y probar automáticamente un servicio implementado. Después, puede probar el servicio utilizando el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe), o su propio cliente, para buscar y corregir cualquier error potencial.  
  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 El cliente de prueba (WcfTestClient.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una herramienta GUI que permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio, y ver la respuesta que devuelve el servicio. Proporciona un servicio de prueba sin problemas cuando se combina con el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 [Generación de clases de tipos de datos a partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos. Las clases definidas en los datos se convertirán en tipos de código.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilización de las herramientas sin el privilegio de administrador  
 Para permitir que los usuarios sin el privilegio de administrador desarrollen servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se crea una ACL (Lista de control de acceso) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada. También permite a los usuarios utilizar el host automático de servicio (wcfSvcHost.exe) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sin concederles los privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta Netsh.exe de [!INCLUDE[wv](../../../includes/wv-md.md)] con la cuenta elevada de administrador. En el siguiente ejemplo se muestra el uso de Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Netsh.exe, consulte [cómo usar la herramienta Netsh.exe y los modificadores de línea de comandos](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Vea también  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
