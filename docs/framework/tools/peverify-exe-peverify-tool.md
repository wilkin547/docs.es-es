---
title: Peverify.exe (Herramienta PEVerify)
description: Use Peverify.exe (comprobación de ejecutable portable) para ayudar a determinar si el código y los metadatos del lenguaje intermedio de Microsoft (MSIL) cumplen los estándares de seguridad de tipos de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
ms.openlocfilehash: b51b01e639719df7ecfde53819e3137813f7c46f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259255"
---
# <a name="peverifyexe-peverify-tool"></a>Peverify.exe (herramienta PEVerify)

La herramienta PEVerify ayuda a los desarrolladores que generan lenguaje intermedio de Microsoft (MSIL) (como autores de compiladores y desarrolladores de motores de scripts) a determinar si el código MSIL y los metadatos asociados satisfacen los requisitos de seguridad de tipos. Algunos compiladores solo generan código con seguridad de tipos comprobable si se evita el uso de determinadas construcciones de lenguaje. Si utiliza un compilador con estas características, conviene que compruebe que no ha puesto en peligro la seguridad de tipos del código. Puede ejecutar la herramienta PEVerify en los archivos con el fin de comprobar el lenguaje MSIL y los metadatos.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).
  
## <a name="syntax"></a>Sintaxis  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|*filename*|Archivo portable ejecutable (PE) para el que se comprueban el lenguaje MSIL y los metadatos.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/break=** *maxErrorCount*|Anula la comprobación si se generan tantos errores como indica *maxErrorCount*.<br /><br /> Este parámetro no es compatible con .NET Framework versión 2.0 o posterior.|  
|**/clock**|Mide los siguientes tiempos de comprobación en milisegundos y los notifica:<br /><br /> **MD Val. cycle**<br /> Ciclo de validación de metadatos<br /><br /> **MD Val. pure**<br /> Validación pura de metadatos<br /><br /> **IL Ver. cycle**<br /> Ciclo de comprobación del Lenguaje intermedio de Microsoft (MSIL)<br /><br /> **IL Ver pure**<br /> Comprobación pura de MSIL<br /><br /> Los valores de **MD Val. cycle** e **IL Ver. cycle** incluyen el tiempo requerido para realizar los procedimientos necesarios de inicio y de cierre. Los valores de **MD Val. pure** e **IL Ver pure** reflejan el tiempo requerido únicamente para realizar la validación o comprobación.|  
|**/help**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/hresult**|Muestra los códigos de error en formato hexadecimal.|  
|**/ignore=** *hex.code* [, *hex.code*]|Omite los códigos de error especificados.|  
|**/ignore=@** *responseFile*|Omite los códigos de error enumerados en el archivo de respuesta especificado.|  
|**/il**|Realiza comprobaciones de la seguridad de tipos de MSIL en los métodos implementados en el ensamblado especificado por *filename*. La herramienta devuelve descripciones detalladas de cada uno de los problemas encontrados, salvo que se especifique la opción **/quiet**.|  
|**/md**|Realiza comprobaciones de validación de metadatos en el ensamblado especificado por *filename*. Esta opción recorre la estructura completa de metadatos en el archivo y genera un informe de todos los problemas de validación encontrados.|  
|**/nologo**|Suprime la presentación de la versión del producto y de la información de copyright.|  
|**/nosymbols**|En .NET Framework versión 2.0, se suprimen los números de línea para la compatibilidad con versiones anteriores.|  
|**/quiet**|Especifica el modo silencioso; suprime la salida de los informes relativos a problemas de comprobación. No obstante, Peverify.exe notifica si el archivo tiene seguridad de tipos, aunque no proporciona información sobre los problemas que impiden comprobar la seguridad de tipos.|  
|`/transparent`|Comprueba solo los métodos transparentes.|  
|**/unique**|Omite la repetición de códigos de error.|  
|**/verbose**|En .NET Framework versión 2.0, se muestra información adicional en los mensajes de comprobación de MSIL.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  

 Common Language Runtime se basa en la ejecución con seguridad de tipos del código de la aplicación para ayudar a imponer mecanismos de aislamiento y seguridad. Normalmente, el código en el que no [se puede comprobar la seguridad de tipos](../../standard/security/key-security-concepts.md#type-safety-and-security) no se puede ejecutar, aunque puede establecer una directiva de seguridad para permitir la ejecución de código de confianza pero que no se puede comprobar.  
  
 Si no se especifican las opciones **/md** o **/il**, Peverify.exe realiza ambos tipos de comprobaciones. Primero realiza comprobaciones de tipo **/md**. Si no hay errores, realiza comprobaciones de tipo **/il**. Si especifica ambas opciones ( **/md** e **/il**), se realizarán comprobaciones de tipo **/il** aunque existan errores en los metadatos. Así, si no hay ningún error de metadatos, **peverify** *filename* equivale a **peverify** *filename* **/md** **/il**.  
  
 Peverify.exe realiza comprobaciones exhaustivas de MSIL basándose en el análisis del flujo de datos y en una lista que contiene centenares de reglas sobre metadatos válidos. Para obtener información detallada sobre las comprobaciones que realiza Peverify.exe, vea las secciones sobre especificaciones para la validación de metadatos y para el conjunto de instrucciones de MSIL en la carpeta Tools Developers Guide de Windows SDK.  
  
.NET Framework versión 2.0 o posterior admite devoluciones de `byref` comprobable especificadas mediante las siguientes instrucciones de MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` y `unbox`.  
  
## <a name="examples"></a>Ejemplos  

 El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`. La herramienta muestra el tiempo necesario para ejecutar estas comprobaciones.  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`. No obstante, Peverify.exe se detiene cuando llega al número máximo de errores (100). La herramienta también omite los códigos de error especificados.  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 El comando siguiente genera el mismo resultado que el ejemplo anterior, pero especifica los códigos de error que se omiten en el archivo de respuesta `ignoreErrors.rsp`.  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 El archivo de respuesta puede contener una lista de códigos de error separados por comas.  
  
```text
0x12345678, 0xABCD1234  
```  
  
 El archivo de respuesta también puede tener un formato que incluya un código de error por línea.  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Escritura de código con seguridad de tipos comprobable](../misc/code-access-security-basics.md#typesafe_code)
- [Seguridad y protección de tipos](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
