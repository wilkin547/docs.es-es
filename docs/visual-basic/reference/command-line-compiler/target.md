---
title: /target (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a8a9fcd6fa6dfaace01f8fbb7fa407145acc16f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="target-visual-basic"></a>/target (Visual Basic)
Especifica el formato de salida del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se resume el efecto de la `/target` opción.  
  
|**Opción**|**Comportamiento**|  
|----------------|------------------|  
|`/target:exe`|Hace que el compilador crear una aplicación de consola ejecutable.<br /><br /> Esta es la opción predeterminada si no `/target` se especifica la opción. El archivo ejecutable se crea con una extensión .exe.<br /><br /> A menos que se especifique lo contrario con la `/out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. Use la `/main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento.|  
|`/target:library`|Hace que el compilador crear una biblioteca de vínculos dinámicos (DLL).<br /><br /> El archivo de biblioteca de vínculos dinámicos se crea con una extensión. dll.<br /><br /> A menos que se especifique lo contrario con los `/out` opción, el nombre de archivo de salida toma el nombre del primer archivo de entrada.<br /><br /> Cuando se crea un archivo DLL, una `Sub Main` procedimiento no es necesario.|  
|`/target:module`|Hace que el compilador genere un módulo que se pueden agregar a un ensamblado.<br /><br /> El archivo de salida se crea con una extensión de archivo .netmodule.<br /><br /> .NET common language runtime no puede cargar un archivo que no tiene un ensamblado. Sin embargo, puede incorporar un archivo en el manifiesto del ensamblado de un ensamblado mediante el uso de `/reference`.<br /><br /> Cuando el código de un módulo hace referencia a los tipos internos de otro módulo, ambos módulos deben incorporarse en un manifiesto del ensamblado mediante el uso de `/reference`.<br /><br /> El [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opción importa los metadatos de un módulo.|  
|`/target:winexe`|Hace que el compilador crear una aplicación ejecutable basado en Windows.<br /><br /> El archivo ejecutable se crea con una extensión .exe. Una aplicación basada en Windows es aquel que proporciona una interfaz de usuario desde el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] biblioteca de clases o con las API de Win32.<br /><br /> A menos que se especifique lo contrario con la `/out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. En casos donde el código tiene más de una clase que tiene un `Sub Main` procedimiento, utilice la `/main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento|  
|`/target:appcontainerexe`|Hace que el compilador crear una aplicación ejecutable basado en Windows que se debe ejecutar en un contenedor de la aplicación. Esta opción está diseñada para usarse para [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] las aplicaciones.<br /><br /> El **por appcontainerexe** configuración establece un bit en el ámbito de las características de la [archivo Portable ejecutable](http://go.microsoft.com/fwlink/p/?LinkId=236960) archivo. Este bit indica que se debe ejecutar la aplicación en un contenedor de la aplicación. Cuando este bit está establecido, se produce un error si el `CreateProcess` método intenta iniciar la aplicación fuera de un contenedor de la aplicación. Además de esta configuración, bits **/target: appcontainerexe** es equivalente a **/target: winexe**.<br /><br /> El archivo ejecutable se crea con una extensión .exe.<br /><br /> A menos que se especifique lo contrario mediante el uso de la `/out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. Si el código contiene más de una clase que tiene un `Sub Main` procedimiento, utilice la `/main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento|  
|`/target:winmdobj`|Hace que el compilador crear un archivo intermedio que se puede convertir en un archivo binario (.winmd) de Windows en tiempo de ejecución. El archivo .winmd puede ser utilizado por programas de JavaScript y C++, además de los programas de lenguajes administrados.<br /><br /> El archivo intermedio se crea con una extensión de .winmdobj.<br /><br /> A menos que se especifique lo contrario mediante el uso de la `/out` opción, el nombre de archivo de salida toma el nombre del primer archivo de entrada. A `Sub Main` procedimiento no es necesario.<br /><br /> El archivo .winmdobj está diseñado para utilizarse como entrada para el <xref:Microsoft.Build.Tasks.WinMDExp> exportar herramienta para producir un archivo de metadatos (WinMD) de Windows. El archivo WinMD tiene una extensión de winmd y contiene el código de la biblioteca original y las definiciones de WinMD que JavaScript, C++ y el uso de Windows en tiempo de ejecución.|  
  
 A menos que especifique `/target:module`, `/target` hace un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] manifiesto del ensamblado para agregarse a un archivo de salida.  
  
 Cada instancia de Vbc.exe produce, como máximo, un archivo de salida. Si especifica una opción del compilador como `/out` o `/target` más de una vez, la última que procese el compilador se coloca en vigor. Información sobre todos los archivos en una compilación se agrega al manifiesto. Todos los archivos resultantes, excepto los creados con `/target:module` contienen metadatos de ensamblado en el manifiesto. Use [Ildasm.exe (Desensamblador de IL)](https://msdn.microsoft.com/library/f7dy01k1) para ver los metadatos en un archivo de salida.  
  
 La forma abreviada de `/target` es `/t`.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>Para establecer /target en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Modifique el valor en el **tipo de aplicación** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `in.vb`, creando `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [entrada/salida (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
