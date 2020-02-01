---
title: Herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 5e7d39062a8ad016eebf949daa625a5ba7848328
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921227"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a>Herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)
El registro de servicio de flujo de trabajo (WFServicesReg.exe) es una herramienta independiente que puede utilizarse para agregar, quitar o reparar los elementos de configuración de los servicios de Windows Workflow Foundation (WF).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a>Notas  
 La herramienta se puede encontrar en la ubicación de instalación de .NET Framework 3,5, específicamente,%windir%\Microsoft.NET\Framework\v3.5 o en%windir%\Microsoft.NET\Framework64\v3.5 en máquinas de 64 bits.  
  
 Las tablas siguientes describen las opciones que pueden utilizarse con la herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe).  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/c`|Configura los servicios de flujo de trabajo de Windows. Se utiliza en escenarios de instalación y reparación.|  
|`/r`|Quita la configuración de los servicios de flujo de trabajo de Windows.|  
|`/v`|Imprime información detallada (para configuración o eliminación).|  
|`/m`|Habilita el formato de registro de MSI.|  
|`/i`|Minimiza la ventana cuando se ejecuta la aplicación.|  
  
## <a name="registration"></a>Registro  
 La herramienta inspecciona el archivo Web.config y registra lo siguiente:  
  
- Ensamblados de referencia de .NET Framework 3,5.  
  
- Proveedor de compilación para archivos .xoml.  
  
- Controladores HTTP para archivos .xoml y .rules.  
  
 La herramienta inspecciona el archivo Machine.config y registra las siguientes extensiones:  
  
- behaviorExtensions  
  
- bindingElementExtensions  
  
- bindingExtensions  
  
 La herramienta también registra los siguientes importadores de metadatos de cliente:  
  
- policyImporters  
  
- wsdlImporters  
  
 La herramienta también registra los controladores y las asignaciones de secuencias de comandos de .xoml y .rules en la metabase de IIS.  
  
 En Windows Server 2003 y equipos con Windows XP (IIS 5,1 e IIS 6,0), se registra un conjunto de asignaciones de scripts. xoml y. rules.  
  
 En equipos de 64 bits, la herramienta registra asignaciones de secuencias de comandos en el modo WOW si el modificador `Enable32BitAppOnWin64` está habilitado, o asignaciones de secuencias de comandos nativas de 64 bits si el modificador `Enable32BitAppOnWin64` está deshabilitado.  
  
 En las máquinas con Windows Vista y Windows Server 2008 (IIS 7,0 y versiones posteriores), se registran dos conjuntos de controladores. xoml y. rules: uno para el modo integrado y otro para el modo clásico.  
  
 En equipos de 64 bits, se registran tres conjuntos de controladores (independientemente del estado del modificador `Enable32BitAppOnWin64`): uno para el modo integrado, otro para el modo clásico de WOW y el tercero para el modo clásico de 64 bits nativo.  
  
> [!NOTE]
> A diferencia de ServiceModelReg.exe, WFServicesReg.exe no permite agregar, quitar o reparar asignaciones de secuencias de comandos o controladores de un sitio web determinado. Para encontrar una solución a este problema, vea la sección "Reparar asignaciones de secuencias de comandos".  
  
## <a name="usage-scenarios"></a>Escenarios de uso  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a>Instalar IIS una vez instalado .NET Framework 3.5  
 En un equipo con Windows Server 2003, .NET Framework 3,5 se instala antes de la instalación de IIS. Debido a la falta de disponibilidad de la metabase de IIS, la instalación de .NET Framework 3,5 se realiza correctamente sin instalar las asignaciones de scripts. xoml y. rules.  
  
 Una vez instalado IIS, puede utilizar la herramienta WFServicesReg.exe con el modificador `/c` para instalar estas asignaciones de secuencias de comandos concretas.  
  
### <a name="repairing-the-scriptmaps"></a>Reparar asignaciones de secuencias de comandos  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a>Asignación de secuencias de comandos eliminada en el nodo de sitios web  
 En un equipo con Windows Server 2003,. xoml o. rules se eliminan accidentalmente del nodo sitios Web. Esto puede repararse ejecutando la herramienta WFServicesReg.exe con el modificador `/c`.  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a>Asignación de secuencias de comandos eliminada en un sitio web determinado  
 En un equipo con Windows Server 2003,. xoml o. rules se eliminan accidentalmente de un sitio Web determinado (por ejemplo, el sitio web predeterminado) en lugar de hacerlo del nodo sitios Web.  
  
 Para reparar los controladores eliminados de un sitio Web determinado, debe ejecutar "WFServicesReg. exe/r" para quitar los controladores de todos los sitios web y, a continuación, ejecutar "WFServicesReg. exe/c" para crear los controladores adecuados para todos los sitios Web.  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a>Configurar los controladores después de cambiar al modo de IIS  
 Cuando IIS está en modo de configuración compartida y .NET Framework está instalado 3,5, la metabase de IIS se configura en una ubicación compartida. Si pasa IIS al modo de configuración no compartido, la metabase local no contendrá los controladores necesarios. Para configurar la metabase local correctamente, puede importar la metabase compartida a local o ejecutar "WFServicesReg. exe/c", que configura la metabase local.
