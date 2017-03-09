---
title: "/target (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/target (opciones del compilador) [Visual Basic]"
  - "target (opciones del compilador) [Visual Basic]"
  - "-target (opciones del compilador) [Visual Basic]"
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# /target (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica el formato del resultado producido por el compilador.  
  
## Sintaxis  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## Comentarios  
 En la tabla siguiente se resume el efecto de la opción `/target`:  
  
|**Opción**|**Comportamiento**|  
|----------------|------------------------|  
|`/target:exe`|Hace que el compilador cree una aplicación de consola ejecutable.<br /><br /> Es la opción predeterminada si no se especifica ninguna opción `/target`.  El archivo ejecutable se crea con la extensión .exe.<br /><br /> A menos que se especifique otra cosa con la opción `/out`, el archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento `Sub Main`.<br /><br /> Sólo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan para producir un archivo .exe.  Utilice la opción `/main` del compilador para especificar qué clase contiene el procedimiento `Sub Main`.|  
|`/target:library`|Hace que el compilador cree una biblioteca de vínculos dinámicos \(archivo DLL\).<br /><br /> El archivo de biblioteca de vínculos dinámicos se crea con la extensión .dll.<br /><br /> A menos que se especifique otra cosa con la opción `/out`, el archivo resultante adopta el nombre del primer archivo de entrada.<br /><br /> Para compilar un archivo DLL no se requiere un procedimiento `Sub Main`.|  
|`/target:module`|Hace que el compilador genere un módulo que se puede agregar a un ensamblado.<br /><br /> El archivo de salida se crea con la extensión .  netmodule.<br /><br /> La biblioteca Common Language Runtime de .NET no puede cargar un archivo que no tenga un ensamblado.  No obstante, puede incorporar ese archivo al manifiesto del ensamblado mediante la opción `/reference`.<br /><br /> Cuando el código de un módulo hace referencia a los tipos internos de otro módulo, ambos módulos deben incorporarse en un manifiesto del ensamblado mediante la opción `/reference`.<br /><br /> La opción [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa metadatos de un módulo.|  
|`/target:winexe`|Hace que el compilador cree una aplicación ejecutable \(EXE\) basada en Windows.<br /><br /> El archivo ejecutable se crea con la extensión .exe.  Una aplicación basada en Windows es la que proporciona una interfaz de usuario para la biblioteca de clases de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] o de las API Win32.<br /><br /> A menos que se especifique otra cosa con la opción `/out`, el archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento `Sub Main`.<br /><br /> Sólo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan para producir un archivo .exe.  En los casos en los que el código tiene varias clases que tienen un procedimiento `Sub Main`, use la opción del compilador `/main` para especificar qué clase contiene el procedimiento `Sub Main`.|  
|`/target:appcontainerexe`|Hace que el compilador para crear una aplicación basada en Windows ejecutable que debe ejecutarse en un contenedor de la aplicación.  Este valor está diseñado para ser usado para aplicaciones de [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] .<br /><br /> **appcontainerexe** a conjuntos un bit en el campo [Ejecutable Portable](http://go.microsoft.com/fwlink/p/?LinkId=236960) de las características del archivo.  Este bit indica que la aplicación se debe ejecutar en un contenedor de la aplicación.  Cuando se establece este bit, se produce un error si los intentos del método de `CreateProcess` para iniciar la aplicación fuera de un contenedor de la aplicación.  Independientemente de este valor de bit, **\/target:appcontainerexe** es equivalente a **\/target:winexe**.<br /><br /> El archivo ejecutable se crea con la extensión .exe.<br /><br /> A menos que se especifique lo contrario mediante la opción de `/out` , el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento de `Sub Main` .<br /><br /> Sólo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan para producir un archivo .exe.  Si el código contiene más de una clase con un procedimiento de `Sub Main` , utilice la opción del compilador `/main` de especificar que la clase contiene el procedimiento de `Sub Main`|  
|`/target:winmdobj`|Hace que el compilador para crear un archivo intermedio que se puede convertir en un archivo binario de Windows en tiempo de ejecución \(.winmd\).  El archivo de .winmd se puede utilizar en programas de JavaScript y C\+\+, además de los programas administrados del lenguaje.<br /><br /> El archivo intermedio se crea con una extensión de .winmdobj.<br /><br /> A menos que se especifique lo contrario mediante la opción de `/out` , el nombre del archivo de salida toma el nombre del primer archivo de entrada.  Un procedimiento de `Sub Main` no se requiere.<br /><br /> El archivo de .winmdobj está diseñado para utilizarse como entrada para que la herramienta de exportación de <xref:Microsoft.Build.Tasks.WinMDExp> mostrar un archivo de \(WinMD\) de metadatos de Windows.  El archivo de WinMD tiene una extensión de .winmd y contiene el código de biblioteca original y las definiciones de WinMD que JavaScript, C\+\+, y el uso de Windows en tiempo de ejecución.|  
  
 A menos que especifique `/target:module`, `/target` provocará un manifiesto del ensamblado [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] que agregará a un archivo de salida.  
  
 Cada instancia de Vbc.exe produce como máximo un archivo de salida.  Si se especifica una opción del compilador como `/out` o `/target` más de una vez, se activará la última que procese el compilador.  La información sobre todos los archivos que intervienen en una compilación se agrega en el manifiesto.  Todos los archivos resultantes, excepto los creados con `/target:module`, contienen metadatos de ensamblado en el manifiesto.  Utilice [Ildasm.exe \(IL Disassembler\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md) para ver los metadatos presentes en un archivo de salida.  
  
 La forma corta de `/target` es `/t`.  
  
### Para establecer \/target en el IDE de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Aplicación**.  
  
3.  Modifique el valor en el cuadro **Tipo de aplicación**.  
  
## Ejemplo  
 El código siguiente compila `in.vb`, con lo que se crea `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [\/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)