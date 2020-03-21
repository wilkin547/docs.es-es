---
title: Utilización de las herramientas de desarrollo de WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183079"
---
# <a name="using-the-wcf-development-tools"></a>Utilización de las herramientas de desarrollo de WCF
En esta sección se describen las herramientas de desarrollo de Visual Studio que pueden ayudarle a desarrollar el WCFservice.  
  
 Puede usar las plantillas de Visual Studio como base para crear rápidamente su propio servicio y, a continuación, usar WCF Service Auto Host y WCF Test Client para depurar y probar el servicio. Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de confirmar un modelo de hospedaje en una fase temprana.  

 > [!NOTE]
 > A partir de Visual Studio 2017, las herramientas de desarrollo de WCF no se instalan de forma predeterminada. Para usar estas características, debe asegurarse de que el componente de Windows Communication Foundation está seleccionado en el instalador de Visual Studio.
  
## <a name="the-wcf-developer-tools"></a>Herramientas de desarrollador de WCF  
 [Plantillas de Visual Studio para WCF](wcf-vs-templates.md)  
  
 Puede usar las plantillas de proyecto y elemento de Visual Studio predefinidas en Visual Studio para compilar rápidamente servicios WCF y aplicaciones circundantes.  
  
 [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 El host automático del servicio WCF (WcfSvcHost.exe) le permite iniciar el depurador de Visual Studio (F5) para hospedar y probar automáticamente un servicio que ha implementado. A continuación, puede probar el servicio mediante el cliente de prueba WCF (wcfTestClient.exe) o su propio cliente para buscar y corregir los posibles errores.  
  
 [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 Cliente de prueba WCF (WcfTestClient.exe) es una herramienta de interfaz gráfica de usuario que le permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio y ver la respuesta que el servicio devuelve. Proporciona una experiencia de prueba de servicio sin problemas cuando se combina con wcf Service Auto Host.  
  
 [Generación de clases de tipos de datos a partir de XML](generating-data-type-classes-from-xml.md)  
  
 Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos. Las clases definidas en los datos se convertirán en tipos de código.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilización de las herramientas sin el privilegio de administrador  
 Para permitir que los usuarios sin privilegios de administrador desarrollenhttp://+:8731/Design_Time_Addressesservicios WCF, se crea una ACL (Lista de control de acceso) para el espacio de nombres " " durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada. También permite a los usuarios usar el host automático del servicio WCF (wcfSvcHost.exe) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta Netsh.exe en Windows Vista en la cuenta de administrador con privilegios elevados. En el siguiente ejemplo se muestra el uso de Netsh.exe.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información acerca de Netsh.exe, vea [Cómo utilizar la herramienta Netsh.exe y](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))los modificadores de línea de comandos .  
  
## <a name="see-also"></a>Consulte también

- [Plantillas de Visual Studio para WCF](wcf-vs-templates.md)
- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
