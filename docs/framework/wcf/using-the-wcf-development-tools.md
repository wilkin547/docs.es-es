---
description: Más información acerca de cómo usar las herramientas de desarrollo de WCF
title: Utilización de las herramientas de desarrollo de WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: c96644fb66006447f6a05f6c08ea84fe2ed99ce8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631702"
---
# <a name="using-the-wcf-development-tools"></a>Utilización de las herramientas de desarrollo de WCF

En esta sección se describen las herramientas de desarrollo de Visual Studio que pueden ayudarle a desarrollar su WCFservice.  
  
 Puede usar las plantillas de Visual Studio como base para compilar rápidamente su propio servicio y, a continuación, utilizar el host automático del servicio WCF y el cliente de prueba WCF para depurar y probar el servicio. Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de confirmar un modelo de hospedaje en una fase temprana.  

 > [!NOTE]
 > A partir de Visual Studio 2017, las herramientas de desarrollo de WCF no se instalan de forma predeterminada. Para poder usar estas características, debe asegurarse de que el componente Windows Communication Foundation está seleccionado en el instalador de Visual Studio.
  
## <a name="the-wcf-developer-tools"></a>Herramientas de desarrollador de WCF  

 [Plantillas de Visual Studio para WCF](wcf-vs-templates.md)  
  
 Puede usar las plantillas de proyecto y elemento predefinidas de Visual Studio en Visual Studio para compilar rápidamente servicios WCF y aplicaciones circundantes.  
  
 [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 El host automático del servicio WCF (WcfSvcHost.exe) permite iniciar el depurador de Visual Studio (F5) para hospedar y probar automáticamente un servicio implementado. Después, puede probar el servicio mediante el cliente de prueba de WCF (wcfTestClient.exe) o su propio cliente para buscar y corregir los posibles errores.  
  
 [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 El cliente de prueba de WCF (WcfTestClient.exe) es una herramienta de GUI que permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio y ver la respuesta que devuelve el servicio. Proporciona una experiencia de pruebas de servicio sin problemas cuando se combina con el host automático del servicio WCF.  
  
 [Generar clases de tipos de datos a partir de XML](generating-data-type-classes-from-xml.md)  
  
 Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos. Las clases definidas en los datos se convertirán en tipos de código.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilización de las herramientas sin el privilegio de administrador  

 Para permitir que los usuarios sin privilegios de administrador desarrollen servicios WCF, se crea una ACL (lista de Access Control) para el espacio de nombres " http://+:8731/Design_Time_Addresses " durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada. También permite a los usuarios utilizar el host automático del servicio WCF (wcfSvcHost.exe) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta de Netsh.exe de Windows Vista con la cuenta de administrador con privilegios elevados. En el siguiente ejemplo se muestra el uso de Netsh.exe.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información sobre Netsh.exe, consulte [uso de la herramienta Netsh.exe y modificadores de Command-Line](/previous-versions/tn-archive/bb490939(v=technet.10)).  
  
## <a name="see-also"></a>Vea también

- [Plantillas de Visual Studio para WCF](wcf-vs-templates.md)
- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
