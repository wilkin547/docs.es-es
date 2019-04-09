---
title: Solución de problemas de instalación
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 41e266ba5b54bfb37313f9588515f7ae9cc6f79d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153080"
---
# <a name="troubleshooting-setup-issues"></a>Solución de problemas de instalación
Este tema describe cómo solucionar problemas de configuración de problemas de Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Algunas claves del Registro de Windows Communication Foundation no se reparan mediante una operación de reparación de MSI en .NET Framework 3.0  
 Si elimina cualquiera de las claves del Registro siguientes:  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Las claves no se vuelven a crear si ejecuta reparación mediante el instalador de .NET Framework 3.0 iniciado desde el **agregar o quitar programas** subprograma en **Panel de Control**. Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Los daños en el servicio WMI bloquean la instalación del proveedor de WMI de Windows Communication Foundation durante la instalación del paquete de .NET Framework 3.0  
 Los daños del servicio WMI pueden bloquear la instalación del proveedor de WMI de Windows Communication Foundation. Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo .mof de WCF mediante el componente mofcomp.exe. A continuación, se muestra una lista de síntomas:  
  
1.  La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.  
  
2.  Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.  
  
3.  El archivo de registro de instalación denominado dd_wcf_retCA* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.  
  
4.  Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication foundation\servicemodel. MOF"  
  
     O bien  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción. ---> System.Runtime.InteropServices.COMException (0 x 80040154): Recuperar el generador de clases COM para el componente con CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} debido al error siguiente: 80040154.  
  
     O bien  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: No se pudo cargar el archivo o ensamblado 'C:\WINDOWS\system32\wbem\mofcomp.exe' o uno de sus dependencias. El sistema no puede encontrar el archivo especificado.  
  
     Nombre del archivo: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Se deben seguir los pasos siguientes para resolver el problema descrito previamente.  
  
1.  Ejecute [la utilidad de diagnóstico WMI, versión 2.0](https://go.microsoft.com/fwlink/?LinkId=94685) para reparar el servicio WMI. Para obtener más información sobre el uso de esta herramienta, consulte el [utilidad de Diagnosis de WMI](https://go.microsoft.com/fwlink/?LinkId=94686) tema.  
  
 Reparar la instalación de .NET Framework 3.0 mediante la **agregar o quitar programas** subprograma ubicado en **Panel de Control**, o desinstale/reinstale .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Reparar .NET Framework 3.0 después de que la instalación de .NET Framework 3.5 quite los elementos de configuración introducidos por .NET Framework 3.5 en el archivo machine.config  
 Si repara .NET Framework 3.0 después de instalar [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], se quitan los elementos de configuración introducidos por [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] en el archivo machine.config. No obstante, el archivo web.config permanece intacto. La solución es reparar [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] después a través de ARP o use el [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` cambie.  
  
 [Herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) puede encontrarse en %windir%\Microsoft.NET\framework\v3.5\ o %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurar IIS correctamente para Webhost de WCF/WF después de instalar .NET Framework 3.5  
 Cuando [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] instalación no puede configurar opciones adicionales de configuración de IIS relacionada con WCF, registra un error en el registro de instalación y continúa. Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios. Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.  
  
 Para solucionar este problema, use el [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` cambie a configurar correctamente asignaciones de secuencias de comandos IIS en el equipo. [Herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) puede encontrarse en %windir%\Microsoft.NET\framework\v3.5\ o %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>No se puede cargar el tipo ‘System.ServiceModel.Activation.HttpModule’ del ensamblado ‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’  
 Este error se produce si [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] está instalado y, a continuación, se habilita la activación HTTP de WCF. Para resolver el problema que se ejecute la siguiente línea de comandos desde dentro de la línea de comandos para desarrolladores para Visual Studio:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de instalación](../../../docs/framework/wcf/samples/set-up-instructions.md)
