---
title: Herramienta de registro de ServiceModel (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: a6f65ccc6caa0a7e496e7de8c83259ab48903753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183102"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>Herramienta de registro de ServiceModel (ServiceModelReg.exe)
Esta herramienta de la línea de comandos proporciona la capacidad de administrar el registro de componentes de WCF y de WF en un único equipo. En circunstancias normales no debería ser necesario usar esta herramienta mientras se configuran e instalan los componentes de WCF y de WF. Pero si experimenta problemas con la activación del servicio, puede intentar registrar los componentes mediante esta herramienta.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Observaciones  
 La herramienta se puede encontrar en la ubicación siguiente:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
> Cuando la herramienta de registro de ServiceModel se ejecuta en Windows Vista, es posible que el cuadro de diálogo Características de **Windows** no refleje que la opción **Activación HTTP** de Windows Communication Foundation en **Microsoft .NET Framework 3.0** está activada. Para acceder al cuadro de diálogo Características de **Windows,** haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar** y, a continuación, escriba **Características opcionales**.  
  
 Las tablas siguientes describen las opciones que se pueden utilizar con ServiceModelReg.exe.  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-ia`|Instala todos los componentes de WCF y de WF.|  
|`-ua`|Desinstala todos los componentes de WCF y de WF.|  
|`-r`|Repara todos los componentes de WCF y de WF.|  
|`-i`|Instala los componentes de WCF y de WF especificados con –c.|  
|`-u`|Desinstala los componentes de WCF y de WF especificados con –c.|  
|`-c`|Instala o desinstala un componente:<br /><br /> - httpnamespace – Reserva de espacio de nombres HTTP<br />- tcpportsharing – Servicio de uso compartido de puertos TCP<br />- tcpactivation: servicio de activación TCP (no compatible con el perfil de cliente de .NET 4)<br />- namedpipeactivation – Servicio de activación de canalización con nombre (no compatible con el perfil de cliente de .NET 4<br />- msmqactivation– servicio de activación de MSMQ (no compatible con el perfil de cliente de .NET 4<br />- etw: manifiestos de seguimiento de eventos ETW (Windows Vista o posterior)|  
|`-q`|Modo silencioso (solo se muestra el registro de errores)|  
|`-v`|Modo detallado.|  
|`-nologo`|Suprime el mensaje del banner y el copyright.|  
|`-?`|Muestra texto de ayuda.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Corregir el error FileLoadException   
 Si instaló versiones anteriores de WCF `FileLoadFoundException` en el equipo, puede obtener un error al ejecutar la herramienta ServiceModelReg para registrar una nueva instalación. Esto puede pasar aun cuando ha quitado manualmente los archivos de la instalación anterior, pero ha dejado intactos los valores machine.config.  
  
 El mensaje de error es similar al siguiente.  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Debería observar en el mensaje de error que el ensamblado de la versión 2.0.0.0 de System.ServiceModel fue instalado por un lanzamiento anterior de Customer Technology Preview (CTP). La versión actual del ensamblado System.ServiceModel que se ha lanzado es 3.0.0.0. Por lo tanto, este problema se produce cuando desea instalar la versión oficial de WCF en un equipo donde se instaló una versión CTP temprana de WCF, pero no completamente desinstalado.  
  
 ServiceModelReg.exe no puede limpiar las entradas de versión anteriores, ni puede registrar las entradas de la nueva versión. La única solución alternativa es editar manualmente machine.config. Puede localizar este archivo en la siguiente ubicación.  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 Si está ejecutando WCF en un equipo de 64 bits, también debe editar el mismo archivo en esta ubicación.  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 Busque los nodos XML de este archivo que hagan referencia a "System.ServiceModel, Version 2.0.0.0", elimínelos y los nodos secundarios. Guarde el archivo y el problema se resolverá volviendo a ejecutar ServiceModelReg.exe.  
  
## <a name="examples"></a>Ejemplos  
 Los ejemplos siguientes muestran cómo usar las opciones más comunes de la herramienta ServiceModelReg.exe.  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
