---
title: Herramienta de registro de ServiceModel (ServiceModelReg.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7032fd6005d5eccf27e0ca34cd89c050260d6e4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
>  Cuando se ejecuta la herramienta de registro ServiceModel en [!INCLUDE[wv](../../../includes/wv-md.md)], **las características de Windows** diálogo podría no reflejar que la **activación HTTP de Windows Communication Foundation** opción bajo **Microsoft .NET Framework 3.0** está activado. El **las características de Windows** cuadro de diálogo se puede acceder haciendo clic en **iniciar**, a continuación, haga clic en **ejecutar** y, a continuación, escriba **OptionalFeatures**.  
  
 Las tablas siguientes describen las opciones que se pueden utilizar con ServiceModelReg.exe.  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-ia`|Instala todos los componentes de WCF y de WF.|  
|`-ua`|Desinstala todos los componentes de WCF y de WF.|  
|`-r`|Repara todos los componentes de WCF y de WF.|  
|`-i`|Instala los componentes de WCF y de WF especificados con –c.|  
|`-u`|Desinstala los componentes de WCF y de WF especificados con –c.|  
|`-c`|Instala o desinstala un componente:<br /><br /> -httpnamespace – reserva de Namespace de HTTP<br />puerto TCP - tcpportsharing – servicio de uso compartido<br />servicio de activación de - tcpactivation-TCP (no admitido en .NET 4 Client Profile)<br />servicio de activación de la canalización con nombre - namedpipeactivation-(no admitido en .NET 4 Client Profile<br />servicio de activación de MSMQ - msmqactivation-(no admitido en .NET 4 Client Profile<br />manifiestos de seguimiento de eventos ETW - etw – (Windows Vista o posterior)|  
|`-q`|Modo silencioso (solo se muestra el registro de errores)|  
|`-v`|Modo detallado.|  
|`-nologo`|Suprime el mensaje del banner y el copyright.|  
|`-?`|Muestra texto de ayuda.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Corregir el error FileLoadException   
 Si ha instalado versiones anteriores de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en su equipo, puede obtener un error `FileLoadFoundException` al ejecutar la herramienta ServiceModelReg para registrar una nueva instalación. Esto puede pasar aun cuando ha quitado manualmente los archivos de la instalación anterior, pero ha dejado intactos los valores machine.config.  
  
 El mensaje de error es similar al siguiente.  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Debería observar en el mensaje de error que el ensamblado de la versión 2.0.0.0 de System.ServiceModel fue instalado por un lanzamiento anterior de Customer Technology Preview (CTP). La versión actual del ensamblado System.ServiceModel que se ha lanzado es 3.0.0.0. Por consiguiente, encontrará este problema cuando desee instalar la versión oficial de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en un equipo donde se instaló una versión CTP anterior de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], pero no se desinstaló completamente.  
  
 ServiceModelReg.exe no puede limpiar las entradas de versión anteriores, ni puede registrar las entradas de la nueva versión. La única solución alternativa es modificar manualmente machine.config. Encontrará este archivo en la ubicación siguiente.  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 Si está ejecutando [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en un equipo de 64 bits, también debe modificar el mismo archivo en esta ubicación.  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 Busque los nodos XML de este archivo que hacen referencia a "System.ServiceModel, Version = 2.0.0.0", elimínelos y elimine también todos los nodos secundarios. Guarde el archivo y el problema se resolverá volviendo a ejecutar ServiceModelReg.exe.  
  
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
