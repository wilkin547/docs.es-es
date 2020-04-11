---
title: Solución de problemas de instalación
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 2cd9ced4f0780b1a6f63e4a5833e20ac91870121
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121580"
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
  
 Las claves no se vuelven a crear si ejecuta la reparación mediante el instalador de .NET Framework 3.0 iniciado desde el applet **Agregar o quitar programas** en el Panel de **control**. Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Los daños en el servicio WMI bloquean la instalación del proveedor de WMI de Windows Communication Foundation durante la instalación del paquete de .NET Framework 3.0  
 Los daños del servicio WMI pueden bloquear la instalación del proveedor de WMI de Windows Communication Foundation. Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo .mof de WCF mediante el componente mofcomp.exe. A continuación, se muestra una lista de síntomas:  
  
1. La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.  
  
2. Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.  
  
3. El archivo de registro de instalación denominado dd_wcf_retCA* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.  
  
4. Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     o:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción. ---> System.Runtime.InteropServices.COMException (0x80040154): Se ha producido un error al recuperar el generador de clases COM para el componente con CLSID (CFSID) -CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA- debido al siguiente error: 80040154.  
  
     o:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: No pudo cargar el archivo ni ensamblado 'C:\WINDOWS\system32\wbem\mofcomp.exe' o uno de sus dependencias. El sistema no encuentra el archivo especificado.  
  
     Nombre del archivo: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Se deben seguir los pasos siguientes para resolver el problema descrito previamente.  
  
1. Ejecute [wMI Diagnosis Utility](https://www.microsoft.com/download/details.aspx?id=7684) para reparar el servicio WMI. Para obtener más información sobre el uso de esta herramienta, consulte Utilidad de [diagnóstico WMI](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Repare la instalación de .NET Framework 3.0 mediante el subprograma **Agregar o quitar programas** ubicado en el **Panel**de control o desinstale o vuelva a instalar .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Reparar .NET Framework 3.0 después de que la instalación de .NET Framework 3.5 quite los elementos de configuración introducidos por .NET Framework 3.5 en el archivo machine.config  
 Si realiza una reparación de .NET Framework 3.0 después de instalar .NET Framework 3.5, se quitan los elementos de configuración introducidos por .NET Framework 3.5 en machine.config. No obstante, el archivo web.config permanece intacto. La solución consiste en reparar .NET Framework 3.5 después de esto a través de `/c` ARP, o usar la herramienta de registro de servicio [WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador.  
  
 [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en %windir%-Microsoft.NET-framework-v3.5 o %windir%-Microsoft.NET-framework64-v3.5-  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurar IIS correctamente para Webhost de WCF/WF después de instalar .NET Framework 3.5  
 Cuando la instalación de .NET Framework 3.5 no puede configurar opciones de configuración de IIS relacionadas con WCF adicionales, registra un error en el registro de instalación y continúa. Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios. Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.  
  
 Para solucionar este problema, utilice la herramienta de registro de `/c` servicio [WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador para configurar correctamente las asignaciones de script de IIS en el equipo. [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en %windir%-Microsoft.NET-framework-v3.5 o %windir%-Microsoft.NET-framework64-v3.5-  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>No se ha podido cargar el tipo 'System.ServiceModel.Activation.HttpModule' desde el ensamblado 'System.ServiceModel, Versión 3.0.0.0, Culture-neutral, PublicKeyToken-b77a5c561934e089'  
 Este error se produce si .NET Framework 4 está instalado y, a continuación, está habilitada la activación HTTP de WCF. Para resolver el problema, ejecute la siguiente línea de comandos desde el símbolo del sistema para desarrolladores de Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de instalación](./samples/set-up-instructions.md)
