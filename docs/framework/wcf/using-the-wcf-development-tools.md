---
title: Utilización de las herramientas de desarrollo de WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 3eb349fd795b2067d4d75ff138fd9b5922110bd3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037882"
---
# <a name="using-the-wcf-development-tools"></a>Utilización de las herramientas de desarrollo de WCF
Esta sección describen las herramientas de desarrollo de Visual Studio que le ayudarán a desarrollar su WCFservice.  
  
 Puede utilizar las plantillas de Visual Studio como base para crear rápidamente su propio servicio y luego usar el Host de servicio WCF y el cliente de prueba WCF para depurar y probar el servicio. Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de adaptarse a un modelo de hospedaje en una fase temprana.  
  
## <a name="the-wcf-developer-tools"></a>Herramientas de desarrollador de WCF  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Puede usar las plantillas de proyecto y elemento predefinidas de Visual Studio en Visual Studio para compilar rápidamente servicios WCF y aplicaciones que lo rodea.  
  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 El Host de servicio WCF (WcfSvcHost.exe) le permite iniciar al depurador de Visual Studio (F5) para hospedar y probar un servicio implementado automáticamente. A continuación, puede probar el servicio mediante el cliente de prueba de WCF (wcfTestClient.exe) o su propio cliente para buscar y corregir cualquier error potencial.  
  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Cliente de prueba de WCF (WcfTestClient.exe) es una herramienta de GUI que permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio y la respuesta del servicio que devuelve la vista. Proporciona un servicio sin problemas las pruebas cuando se combina con el Host de servicio WCF.  
  
 [Generación de clases de tipos de datos a partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos. Las clases definidas en los datos se convertirán en tipos de código.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilización de las herramientas sin el privilegio de administrador  
 Para permitir que los usuarios sin privilegios de administrador desarrollar los servicios WCF, se crea una ACL (lista de Control de acceso) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada. También permite a los usuarios utilizar al Host de servicio WCF (wcfSvcHost.exe) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta Netsh.exe de [!INCLUDE[wv](../../../includes/wv-md.md)] con la cuenta elevada de administrador. En el siguiente ejemplo se muestra el uso de Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información sobre Netsh.exe, consulte [cómo usar la herramienta Netsh.exe y los modificadores de línea de comandos](https://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Vea también  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
