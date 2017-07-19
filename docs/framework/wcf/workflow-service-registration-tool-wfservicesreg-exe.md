---
title: "Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe)
El registro de servicio de flujo de trabajo \(WFServicesReg.exe\) es una herramienta independiente que puede utilizarse para agregar, quitar o reparar los elementos de configuración de los servicios de Windows Workflow Foundation \(WF\).  
  
## Sintaxis  
  
```  
  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## Comentarios  
 La herramienta se encuentra en la ubicación de instalación [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], concretamente, en %windir%\\Microsoft.NET\\Framework\\v3.5 o, en el caso de equipos de 64 bits, en %windir%\\Microsoft.NET\\Framework64\\v3.5.  
  
 Las tablas siguientes describen las opciones que pueden utilizarse con la herramienta de registro de servicio de flujo de trabajo \(WFServicesReg.exe\).  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/c`|Configura los servicios de flujo de trabajo de Windows.Se utiliza en escenarios de instalación y reparación.|  
|`/r`|Quita la configuración de los servicios de flujo de trabajo de Windows.|  
|`/v`|Imprime información detallada \(para configuración o eliminación\).|  
|`/m`|Habilita el formato de registro de MSI.|  
|`/i`|Minimiza la ventana cuando se ejecuta la aplicación.|  
  
## Registro  
 La herramienta inspecciona el archivo Web.config y registra lo siguiente:  
  
-   Ensamblados de referencia [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].  
  
-   Proveedor de compilación para archivos .xoml.  
  
-   Controladores HTTP para archivos .xoml y .rules.  
  
 La herramienta inspecciona el archivo Machine.config y registra las siguientes extensiones:  
  
-   behaviorExtensions  
  
-   bindingElementExtensions  
  
-   bindingExtensions  
  
 La herramienta también registra los siguientes importadores de metadatos de cliente:  
  
-   policyImporters  
  
-   wsdlImporters  
  
 La herramienta también registra los controladores y las asignaciones de secuencias de comandos de .xoml y .rules en la metabase de IIS.  
  
 En equipos [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../includes/wxp-md.md)] \(IIS 5.1 e [!INCLUDE[iis601](../../../includes/iis601-md.md)]\), se registra un conjunto de asignaciones de secuencias de comandos de .xoml y .rules.  
  
 En equipos de 64 bits, la herramienta registra asignaciones de secuencias de comandos en el modo WOW si el modificador `Enable32BitAppOnWin64` está habilitado, o asignaciones de secuencias de comandos nativas de 64 bits si el modificador `Enable32BitAppOnWin64` está deshabilitado.  
  
 En equipos [!INCLUDE[wv](../../../includes/wv-md.md)] y Windows Server 2008 \(IIS 7.0 y anteriores\), se registran dos conjuntos de controladores .xoml y .rules: uno para el modo integrado y uno para el modo clásico.  
  
 En equipos de 64 bits, se registran tres conjuntos de controladores \(independientemente del estado del modificador `Enable32BitAppOnWin64`\): uno para el modo integrado, otro para el modo clásico de WOW y el tercero para el modo clásico de 64 bits nativo.  
  
> [!NOTE]
>  A diferencia de ServiceModelReg.exe, WFServicesReg.exe no permite agregar, quitar o reparar asignaciones de secuencias de comandos o controladores de un sitio web determinado.Para encontrar una solución a este problema, vea la sección "Reparar asignaciones de secuencias de comandos".  
  
## Escenarios de uso  
  
### Instalar IIS una vez instalado .NET Framework 3.5  
 En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], se instala [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] antes que IIS.Debido a la falta de disponibilidad de la metabase de IIS, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] se instala correctamente sin instalar las asignaciones de secuencias de comandos de .xoml y .rules.  
  
 Una vez instalado IIS, puede utilizar la herramienta WFServicesReg.exe con el modificador `/c` para instalar estas asignaciones de secuencias de comandos concretas.  
  
### Reparar asignaciones de secuencias de comandos  
  
#### Asignación de secuencias de comandos eliminada en el nodo de sitios web  
 En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], los archivos .xoml o .rules se eliminaron accidentalmente del nodo de sitios web.Esto puede repararse ejecutando la herramienta WFServicesReg.exe con el modificador `/c`.  
  
#### Asignación de secuencias de comandos eliminada en un sitio web determinado  
 En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .los archivos xoml o .rules se eliminaron accidentalmente de un sitio web determinado \(por ejemplo, el sitio web predeterminado\), en lugar de eliminarse del nodo de sitios web.  
  
 Para reparar los controladores eliminados de un sitio web concreto, ejecute "WFServicesReg.exe \/r" para quitar los controladores de todos los sitios web y, a continuación, ejecute "WFServicesReg.exe \/c" para crear los controladores adecuados para todos los sitios web.  
  
### Configurar los controladores después de cambiar al modo de IIS  
 Cuando IIS está en modo de configuración compartido y se instala [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], la metabase de IIS se configura en una ubicación compartida.Si pasa IIS al modo de configuración no compartido, la metabase local no contendrá los controladores necesarios.Para configurar correctamente la metabase local, puede importar la metabase compartida a local, o ejecutar "WFServicesReg.exe \/c", que configura la metabase local.