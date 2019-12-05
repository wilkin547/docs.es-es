---
title: Solución de problemas de instalación
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: becf2576528dc0011a77597b3665d77f6907a3cc
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802432"
---
# <a name="troubleshooting-setup-issues"></a>Solución de problemas de instalación
En este tema se describe cómo solucionar problemas de configuración de Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Algunas claves del Registro de Windows Communication Foundation no se reparan mediante una operación de reparación de MSI en .NET Framework 3.0  
 Si elimina cualquiera de las claves del Registro siguientes:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Las claves no se vuelven a crear si ejecuta la reparación con el instalador .NET Framework 3,0 iniciado desde el applet **Agregar o quitar programas** del **Panel de control**. Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Los daños en el servicio WMI bloquean la instalación del proveedor de WMI de Windows Communication Foundation durante la instalación del paquete de .NET Framework 3.0  
 Los daños del servicio WMI pueden bloquear la instalación del proveedor de WMI de Windows Communication Foundation. Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo .mof de WCF mediante el componente mofcomp.exe. A continuación, se muestra una lista de síntomas:  
  
1. La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.  
  
2. Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.  
  
3. El archivo de registro de instalación denominado dd_wcf_retCA* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.  
  
4. Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     o bien:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción. ---> System. Runtime. InteropServices. COMException (0x80040154): no se pudo recuperar el generador de clases COM para el componente con CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} debido al siguiente error: 80040154.  
  
     o bien:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: No pudo cargar el archivo ni ensamblado 'C:\WINDOWS\system32\wbem\mofcomp.exe' o uno de sus dependencias. El sistema no puede encontrar el archivo especificado.  
  
     Nombre del archivo: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Se deben seguir los pasos siguientes para resolver el problema descrito previamente.  
  
1. Ejecute [el utilidad de diagnóstico de WMI, versión 2,0](https://go.microsoft.com/fwlink/?LinkId=94685) para reparar el servicio WMI. Para obtener más información sobre el uso de esta herramienta, consulte el artículo [utilidad de diagnóstico de WMI](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10)) .  
  
 Repare la instalación de .NET Framework 3,0 mediante el applet **Agregar o quitar programas** que se encuentra en el **Panel de control**, o bien desinstale o vuelva a instalar el .NET Framework 3,0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Reparar .NET Framework 3.0 después de que la instalación de .NET Framework 3.5 quite los elementos de configuración introducidos por .NET Framework 3.5 en el archivo machine.config  
 Si realiza una reparación de .NET Framework 3,0 después de instalar .NET Framework 3,5, se quitan los elementos de configuración introducidos por .NET Framework 3,5 en el archivo Machine. config. No obstante, el archivo web.config permanece intacto. La solución consiste en reparar .NET Framework 3,5 después de hacerlo a través de ARP, o usar la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg. exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador `/c`.  
  
 La [herramienta de registro de servicio de flujo de trabajo (WFServicesReg. exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurar IIS correctamente para Webhost de WCF/WF después de instalar .NET Framework 3.5  
 Cuando .NET Framework instalación 3,5 no puede configurar otras opciones de configuración de IIS relacionadas con WCF, registra un error en el registro de instalación y continúa. Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios. Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.  
  
 Para solucionar este problema, use la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg. exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador `/c` para configurar correctamente las asignaciones de script de IIS en la máquina. La [herramienta de registro de servicio de flujo de trabajo (WFServicesReg. exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>No se puede cargar el tipo ‘System.ServiceModel.Activation.HttpModule’ del ensamblado ‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’  
 Este error se produce si .NET Framework 4 está instalado y, a continuación, se habilita la activación HTTP de WCF. Para resolver el problema, ejecute la siguiente línea de comandos desde el Símbolo del sistema para desarrolladores para Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de instalación](./samples/set-up-instructions.md)
