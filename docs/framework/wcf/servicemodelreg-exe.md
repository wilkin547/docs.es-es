---
title: Herramienta de registro de ServiceModel (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 5fab1a356cd035ed006bfe90d713e179907e0137
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051798"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>Herramienta de registro de ServiceModel (ServiceModelReg.exe)
Esta herramienta de la línea de comandos proporciona la capacidad de administrar el registro de componentes de WCF y de WF en un único equipo. En circunstancias normales no debería ser necesario usar esta herramienta mientras se configuran e instalan los componentes de WCF y de WF. Pero si experimenta problemas con la activación del servicio, puede intentar registrar los componentes mediante esta herramienta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Comentarios  
 La herramienta se puede encontrar en la ubicación siguiente:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
>  Cuando se ejecuta la herramienta de registro de ServiceModel en [!INCLUDE[wv](../../../includes/wv-md.md)], **características de Windows** diálogo podría no reflejar que el **activación HTTP de Windows Communication Foundation** opción bajo **Microsoft .NET Framework 3.0** está activado. El **características de Windows** diálogo puede tener acceso haciendo clic en **iniciar**, a continuación, haga clic en **ejecutar** y, a continuación, escriba **OptionalFeatures**.  
  
 Las tablas siguientes describen las opciones que se pueden utilizar con ServiceModelReg.exe.  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-ia`|Instala todos los componentes de WCF y de WF.|  
|`-ua`|Desinstala todos los componentes de WCF y de WF.|  
|`-r`|Repara todos los componentes de WCF y de WF.|  
|`-i`|Instala los componentes de WCF y de WF especificados con –c.|  
|`-u`|Desinstala los componentes de WCF y de WF especificados con –c.|  
|`-c`|Instala o desinstala un componente:<br /><br /> -httpnamespace – reserva de Namespace HTTP<br />puerto TCP - tcpportsharing – servicio de uso compartido<br />servicio de activación - tcpactivation TCP (no admitido en .NET 4 Client Profile)<br />servicio - namedpipeactivation-activación de canalización con nombre (no admitido en .NET 4 Client Profile<br />servicio de activación de MSMQ - msmqactivation-(no admitido en .NET 4 Client Profile<br />ETW - etw – manifiestos de seguimiento de eventos (Windows Vista o versiones posteriores)|  
|`-q`|Modo silencioso (solo se muestra el registro de errores)|  
|`-v`|Modo detallado.|  
|`-nologo`|Suprime el mensaje del banner y el copyright.|  
|`-?`|Muestra texto de ayuda.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Corregir el error FileLoadException   
 Si instaló versiones anteriores de WCF en su equipo, es posible que obtenga un `FileLoadFoundException` error al ejecutar la herramienta ServiceModelReg para registrar una nueva instalación. Esto puede pasar aun cuando ha quitado manualmente los archivos de la instalación anterior, pero ha dejado intactos los valores machine.config.  
  
 El mensaje de error es similar al siguiente.  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Debería observar en el mensaje de error que el ensamblado de la versión 2.0.0.0 de System.ServiceModel fue instalado por un lanzamiento anterior de Customer Technology Preview (CTP). La versión actual del ensamblado System.ServiceModel que se ha lanzado es 3.0.0.0. Por lo tanto, este problema se produce cuando va a instalar la versión oficial de WCF en un equipo donde se instaló una versión CTP de WCF, pero completamente no desinstala.  
  
 ServiceModelReg.exe no puede limpiar las entradas de versión anteriores, ni puede registrar las entradas de la nueva versión. La única solución alternativa es modificar manualmente machine.config. Encontrará este archivo en la ubicación siguiente.  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 Si usa WCF en un equipo de 64 bits, también debe editar el mismo archivo en esta ubicación.  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 Busque los nodos XML de este archivo que hacen referencia a "System.ServiceModel, Version = 2.0.0.0", elimínelos y elimine también los nodos secundarios. Guarde el archivo y el problema se resolverá volviendo a ejecutar ServiceModelReg.exe.  
  
## <a name="examples"></a>Ejemplos  
 Los ejemplos siguientes muestran cómo usar las opciones más comunes de la herramienta ServiceModelReg.exe.  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
