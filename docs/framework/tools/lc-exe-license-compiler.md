---
title: "Lc.exe (License Compiler) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Lc.exe"
  - ".licx file"
  - "License Compiler"
  - "control licenses [Windows Forms]"
  - "compiling licenses file"
  - "license file"
  - ".licenses file"
  - "Windows Forms, control licenses"
  - "licensed controls [Windows Forms]"
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Lc.exe (License Compiler)
El Compilador de licencias lee archivos de texto que contienen información sobre licencias y crea un archivo binario que se puede incrustar como recurso en un archivo ejecutable de Common Language Runtime.  
  
 El Diseñador de Windows Forms genera o actualiza automáticamente un archivo de texto .licx siempre que se agrega al formulario un control con licencia.  Como parte de la compilación, el sistema del proyecto transforma el archivo de texto .licx en un recurso binario .licenses que proporciona compatibilidad para la licencia de controles .NET.  A continuación, el recurso binario se incrustará en los resultados del proyecto.  
  
 No se admite la compilación cruzada entre 32 y 64 bits cuando se usa la herramienta Compilador de licencias al generar el proyecto.  Esto se debe a que el Compilador de licencias tiene que cargar los ensamblados, y no se permite cargar ensamblados de 64 bits de una aplicación de 32 bits y viceversa.  En este caso, utilice el Compilador de licencias desde la línea de comandos para compilar la licencia manualmente y especifique la arquitectura correspondiente.  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## Sintaxis  
  
```  
  
        lc /target:  
        targetPE /complist:filename [/outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/complist:** *nombreArchivo*|Especifica el nombre de un archivo que contiene la lista de componentes con licencia que se van a incluir en el archivo .licenses.  Se hace referencia a cada componente utilizando su nombre completo con un solo componente por línea.<br /><br /> Los usuarios de la línea de comandos pueden especificar un archivo independiente para cada formulario del proyecto.  Lc.exe acepta varios archivos de entrada y crea un único archivo .licenses.|  
|**\/h**\[**elp**\]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**\/i:** *módulo*|Especifica los módulos que contienen los componentes enumerados en el archivo **\/complist**.  Para especificar más de un módulo, utilice varias marcas **\/i**.|  
|**\/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**\/outdir:** *rutaAcceso*|Especifica el directorio en el que se coloca el archivo .licenses de resultados.|  
|**\/target:** *PEDeDestino*|Especifica el archivo ejecutable para el que se genera el archivo .licenses.|  
|**\/v**|Especifica el modo detallado; muestra información del progreso de la compilación.|  
|**@** *file*|Especifica el archivo de respuesta \(.rsp\).|  
|**\/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## Ejemplo  
  
1.  Si utiliza un control con licencia `MyCompany.Samples.LicControl1` dentro de `Samples.DLL` en una aplicación denominada `HostApp.exe`*,* puede crear un archivo `HostAppLic.txt` que contenga lo siguiente.  
  
    ```  
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2.  Se puede crear el archivo .licenses denominado `HostApp.exe.licenses` utilizando el comando siguiente.  
  
    ```  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3.  Se puede compilar el archivo `HostApp.exe` que incluya el archivo .licenses como un recurso.  Si está compilando una aplicación en C\#, debe utilizar el comando siguiente para compilarla.  
  
    ```  
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 El comando siguiente compila `myApp.licenses` a partir de las listas de componentes con licencia especificadas por `hostapplic.txt`, `hostapplic2.txt` y `hostapplic3.txt`.  El argumento `modulesList` especifica los módulos que contienen los componentes con licencia.  
  
```  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## Ejemplo de archivo de respuesta  
 La siguiente lista muestra un ejemplo de un archivo de respuesta, `response.rsp`.  Para obtener más información acerca de los archivos de respuesta, consulte [Archivos de respuesta](../Topic/MSBuild%20Response%20Files.md).  
  
```  
/target:hostapp.exe  
/complist:hostapplic.txt   
/i:WFCPrj.dll   
/outdir:"C:\My Folder"  
  
```  
  
 La siguiente línea de comandos utiliza el archivo `response.rsp`.  
  
```  
lc @response.rsp  
```  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Al.exe \(Assembly Linker\)](../../../docs/framework/tools/al-exe-assembly-linker.md)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)