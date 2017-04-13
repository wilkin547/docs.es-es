---
title: "Soluci&#243;n de problemas de instalaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Soluci&#243;n de problemas de instalaci&#243;n
En este tema se describe cómo solucionar problemas de la instalación de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Algunas claves del Registro de Windows Communication Foundation no se reparan mediante una operación de reparación de MSI en .NET Framework 3.0  
 Si elimina cualquiera de las claves del Registro siguientes:  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelService 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelOperation 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SMSvcHost 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSDTC Bridge 3.0.0.0  
  
 No se recrean las claves si ejecuta la reparación utilizando el instalador de .NET Framework 3.0 iniciado desde el applet **Agregar o quitar programas** en el **Panel de control**.Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.  
  
## Los daños en el servicio WMI bloquean la instalación del proveedor de WMI de Windows Communication Foundation durante la instalación del paquete de .NET Framework 3.0  
 Los daños del servicio WMI pueden bloquear la instalación del proveedor de WMI de Windows Communication Foundation.Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo .mof de WCF mediante el componente mofcomp.exe.A continuación, se muestra una lista de síntomas:  
  
1.  La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.  
  
2.  Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.  
  
3.  El archivo de registro de instalación denominado dd\_wcf\_retCA\* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.  
  
4.  Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:  
  
     ServiceModelReg \[11:09:59:046\]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\\WINDOWS\\system32\\wbem\\mofcomp.exe con "E:\\WINDOWS\\Microsoft.NET\\Framework\\v3.0\\Windows Communication Foundation\\ServiceModel.mof"  
  
     O bien:  
  
     ServiceModelReg \[07:19:33:843\]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción.\-\-\-\> System.Runtime.InteropServices.COMException \(0x80040154\): No se pudo recuperar el generador de clases COM para el componente con CLSID {CF4CC405\-E2C5\-4DDD\-B3CE\-5E7582D8C9FA} debido al error siguiente: 80040154.  
  
     O bien:  
  
     ServiceModelReg \[07:19:32:750\]: System.IO.FileNotFoundException: No pudo cargar el archivo ni ensamblado 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe' o uno de sus dependencias.El sistema no puede encontrar el archivo especificado.  
  
     Nombre del archivo: 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe  
  
 Se deben seguir los pasos siguientes para resolver el problema descrito previamente.  
  
1.  Ejecute [la utilidad de diagnóstico de WMI, versión 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) para reparar el servicio WMI.[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo usar esta herramienta, vea el tema [Utilidad de diagnóstico de WMI](http://go.microsoft.com/fwlink/?LinkId=94686).  
  
 Repare la instalación de .NET Framework 3.0 utilizando el applet **Agregar o quitar programas** situado en el **Panel de control** o desinstale\/reinstale .NET Framework 3.0.  
  
## Reparar .NET Framework 3.0 después de que la instalación de .NET Framework 3.5 quite los elementos de configuración introducidos por .NET Framework 3.5 en el archivo machine.config  
 Si repara .NET Framework 3.0 después de instalar [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], se quitan los elementos de configuración introducidos por [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] en el archivo machine.config.No obstante, el archivo web.config permanece intacto.La solución es reparar [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] después a través de ARP o, utilizar la [Herramienta de registro de servicio de flujo de trabajo \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador `/c`.  
  
 [Herramienta de registro de servicio de flujo de trabajo \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) puede encontrarse en %windir%\\Microsoft.NET\\framework\\v3.5\\ o %windir%\\Microsoft.NET\\framework64\\v3.5\\  
  
## Configurar IIS correctamente para Webhost de WCF\/WF después de instalar .NET Framework 3.5  
 Cuando la instalación de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] no puede configurar valores de configuración IIS adicionales relacionados con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], registra un error en el registro de instalación y continúa.Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios.Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.  
  
 Como la solución alternativa a este problema, use [Herramienta de registro de servicio de flujo de trabajo \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con el modificador `/c` para configurar correctamente asignaciones de scripts de IIS en el equipo.[Herramienta de registro de servicio de flujo de trabajo \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) puede encontrarse en %windir%\\Microsoft.NET\\framework\\v3.5\\ o %windir%\\Microsoft.NET\\framework64\\v3.5\\  
  
## No se puede cargar el tipo ‘System.ServiceModel.Activation.HttpModule’ del ensamblado ‘System.ServiceModel, Version 3.0.0.0, Culture\=neutral, PublicKeyToken\=b77a5c561934e089’  
 Este error se produce si se instala [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] y, a continuación, se habilita la activación HTTP de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Para resolver el problema ejecute la siguiente línea de comandos desde el símbolo del sistema de [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## Vea también  
 [Instrucciones de instalación](../../../docs/framework/wcf/samples/set-up-instructions.md)