---
title: Lc.exe (Compilador de licencias)
description: Use Lc.exe, el compilador de licencias. Esta herramienta lee los archivos de texto que tienen información de licencia y crea un archivo binario para insertarlo en un ejecutable de CLR como un recurso.
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 1a9806cd71f9990d9ce70b35b3af760a22347003
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258808"
---
# <a name="lcexe-license-compiler"></a>Lc.exe (Compilador de licencias)

El Compilador de licencias lee archivos de texto que contienen información sobre licencias y crea un archivo binario que se puede incrustar como recurso en un archivo ejecutable de Common Language Runtime.  
  
 El Diseñador de Windows Forms genera o actualiza automáticamente un archivo de texto .licx siempre que se agrega al formulario un control con licencia. Como parte de la compilación, el sistema del proyecto transforma el archivo de texto .licx en un recurso binario .licenses que proporciona compatibilidad para la licencia de controles .NET. A continuación, el recurso binario se incrustará en los resultados del proyecto.  
  
 No se admite la compilación cruzada entre 32 y 64 bits cuando se usa la herramienta Compilador de licencias al generar el proyecto. Esto se debe a que el Compilador de licencias tiene que cargar los ensamblados, y no se permite cargar ensamblados de 64 bits de una aplicación de 32 bits y viceversa. En este caso, utilice el Compilador de licencias desde la línea de comandos para compilar la licencia manualmente y especifique la arquitectura correspondiente.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/complist:** *filename*|Especifica el nombre de un archivo que contiene la lista de componentes con licencia que se van a incluir en el archivo .licenses. Se hace referencia a cada componente utilizando su nombre completo con un solo componente por línea.<br /><br /> Los usuarios de la línea de comandos pueden especificar un archivo independiente para cada formulario del proyecto. Lc.exe acepta varios archivos de entrada y crea un único archivo .licenses.|  
|**/h**[**elp**]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/i:** *module*|Especifica los módulos que contienen los componentes enumerados en el archivo **/complist**. Para especificar más de un módulo, use varias marcas **/i**.|  
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**/outdir:** *path*|Especifica el directorio en el que se coloca el archivo .licenses de resultados.|  
|**/target:** *targetPE*|Especifica el archivo ejecutable para el que se genera el archivo .licenses.|  
|**/v**|Especifica el modo detallado; muestra información del progreso de la compilación.|  
|**@** *file*|Especifica el archivo de respuesta (.rsp).|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="example"></a>Ejemplo  
  
1. Si usa un control con licencia `MyCompany.Samples.LicControl1` dentro de `Samples.DLL` en una aplicación denominada `HostApp.exe` *,*  puede crear un archivo `HostAppLic.txt` que contenga lo siguiente.  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. Se puede crear el archivo .licenses denominado `HostApp.exe.licenses` utilizando el comando siguiente.  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. Se puede compilar el archivo `HostApp.exe` que incluya el archivo .licenses como un recurso. Si está compilando una aplicación en C#, debe utilizar el comando siguiente para compilarla.  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 El comando siguiente compila `myApp.licenses` a partir de las listas de componentes con licencia especificadas por `hostapplic.txt`, `hostapplic2.txt` y `hostapplic3.txt`. El argumento `modulesList` especifica los módulos que contienen los componentes con licencia.  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a>Ejemplo de archivo de respuesta  

 La siguiente lista muestra un ejemplo de un archivo de respuesta, `response.rsp`. Para más información sobre los archivos de respuesta, consulte [Archivos de respuesta](/visualstudio/msbuild/msbuild-response-files).  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 La siguiente línea de comandos usa el archivo `response.rsp`.  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Al.exe (Assembly Linker)](al-exe-assembly-linker.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
