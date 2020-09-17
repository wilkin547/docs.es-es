---
title: Solución de problemas de instalación
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: fb687e9975ab9ac763030f10d54c7744dc02c9e0
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720457"
---
# <a name="troubleshoot-setup-issues"></a>Solucionar problemas de configuración

En este artículo se describe cómo solucionar problemas de configuración de Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Algunas claves del Registro de Windows Communication Foundation no se reparan mediante una operación de reparación de MSI en .NET Framework 3.0  
 Si elimina cualquiera de las claves del Registro siguientes:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Las claves no se vuelven a crear si ejecuta la reparación con el instalador .NET Framework 3,0 iniciado desde el applet **Agregar o quitar programas** del **Panel de control**. Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-wmi-provider"></a>Daños en el servicio WMI la instalación del proveedor WMI

 Los daños en el servicio WMI pueden bloquear la instalación del Windows Communication Foundation proveedor WMI al instalar el paquete .NET Framework 3,0. Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo WCF *. mof* mediante el componente *mofcomp.exe* . A continuación, se muestra una lista de síntomas:  
  
1. La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.  
  
2. Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.  
  
3. El archivo de registro de instalación denominado dd_wcf_retCA* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.  
  
4. Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     o:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción. ---> System. Runtime. InteropServices. COMException (0x80040154): no se pudo recuperar el generador de clases COM para el componente con CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} debido al siguiente error: 80040154.  
  
     o:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: No pudo cargar el archivo ni ensamblado 'C:\WINDOWS\system32\wbem\mofcomp.exe' o uno de sus dependencias. El sistema no encuentra el archivo especificado.  
  
     Nombre del archivo: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Se deben seguir los pasos siguientes para resolver el problema descrito previamente.  
  
1. Ejecute el Utilidad de diagnóstico de WMI para reparar el servicio WMI. Para obtener más información sobre el uso de esta herramienta, vea [utilidad de diagnóstico de WMI](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Repare la instalación de .NET Framework 3,0 mediante el applet **Agregar o quitar programas** que se encuentra en el **Panel de control**, o bien desinstale o vuelva a instalar el .NET Framework 3,0.  
  
## <a name="repair-net-framework-30-after-net-framework-35-installation"></a>Reparar .NET Framework 3,0 después de la instalación de .NET Framework 3,5

 Si realiza una reparación de .NET Framework 3,0 después de instalar .NET Framework 3,5, se quitan los elementos de configuración introducidos por .NET Framework 3,5 en *machine.config* . Sin embargo, el archivo de *web.config* permanece intacto. La solución consiste en reparar .NET Framework 3,5 después de hacerlo a través de ARP, o usar la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` modificador.  
  
 La [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurar IIS correctamente para Webhost de WCF/WF después de instalar .NET Framework 3.5  
 Cuando .NET Framework instalación 3,5 no puede configurar otras opciones de configuración de IIS relacionadas con WCF, registra un error en el registro de instalación y continúa. Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios. Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.  
  
 Para solucionar este problema, use la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` modificador para configurar correctamente las asignaciones de script de IIS en la máquina. La [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule"></a>No se pudo cargar el tipo ' System. ServiceModel. Activation. HttpModule '

**No se pudo cargar el tipo ' System. ServiceModel. Activation. HttpModule ' del ensamblado ' System. ServiceModel, version 3.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089 '**

 Este error se produce si .NET Framework 4 está instalado y, a continuación, se habilita la activación HTTP de WCF. Para resolver el problema, ejecute el siguiente comando desde el Símbolo del sistema para desarrolladores para Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de instalación](./samples/set-up-instructions.md)
