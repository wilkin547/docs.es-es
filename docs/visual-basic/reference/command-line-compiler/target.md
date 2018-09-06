---
title: -target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17528bb9faf137029b35e4a9f28bab7a28ae25db
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864620"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)
Especifica el formato de salida del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se resume el efecto de la `-target` opción.  
  
|**Opción**|**Comportamiento**|  
|----------------|------------------|  
|`-target:exe`|Hace que el compilador cree una aplicación de consola ejecutable.<br /><br /> Esta es la opción predeterminada cuando no hay ninguna `-target` se especifica la opción. Con la extensión .exe, se crea el archivo ejecutable.<br /><br /> A menos que se especifique lo contrario con la `/out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. Use la `-main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento.|  
|`-target:library`|Hace que el compilador cree una biblioteca de vínculos dinámicos (DLL).<br /><br /> Se crea el archivo de biblioteca de vínculos dinámicos con una extensión. dll.<br /><br /> A menos que se especifique lo contrario con la `-out` opción, el nombre de archivo de salida toma el nombre del primer archivo de entrada.<br /><br /> Al compilar un archivo DLL, un `Sub Main` procedimiento no es necesario.|  
|`-target:module`|Hace que el compilador genere un módulo que se puede agregar a un ensamblado.<br /><br /> El archivo de salida se crea con la extensión .netmodule.<br /><br /> .NET common language runtime no puede cargar un archivo que no tiene un ensamblado. Sin embargo, puede incorporar este archivo en el manifiesto del ensamblado de un ensamblado mediante el uso de `-reference`.<br /><br /> Cuando el código de un módulo hace referencia a los tipos internos de otro módulo, se deben incorporar ambos módulos en un manifiesto del ensamblado mediante el uso de `-reference`.<br /><br /> El [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opción importa metadatos de un módulo.|  
|`-target:winexe`|Hace que el compilador cree una aplicación ejecutable basado en Windows.<br /><br /> Con la extensión .exe, se crea el archivo ejecutable. Una aplicación basada en Windows es aquel que proporciona una interfaz de usuario desde el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] biblioteca de clases o con las API de Win32.<br /><br /> A menos que se especifique lo contrario con la `-out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. En casos donde el código tiene más de una clase que tiene un `Sub Main` procedimiento, utilice el `-main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento|  
|`-target:appcontainerexe`|Hace que el compilador cree una aplicación ejecutable basado en Windows que se debe ejecutar en un contenedor de aplicaciones. Esta opción está diseñada para usarse para [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] aplicaciones.<br /><br /> El **appcontainerexe** configuración establece un bit en el campo de las características de la [Portable ejecutable](/windows/desktop/Debug/pe-format) archivo. Este bit indica que se debe ejecutar la aplicación en un contenedor de aplicaciones. Cuando este bit se establece, se produce un error si el `CreateProcess` método intenta iniciar la aplicación fuera de un contenedor de aplicaciones. Aparte de esta configuración, bits **-target: appcontainerexe** es equivalente a **-target: winexe**.<br /><br /> Con la extensión .exe, se crea el archivo ejecutable.<br /><br /> A menos que se especifique lo contrario mediante el uso de la `-out` opción, el nombre de archivo de salida toma el nombre del archivo de entrada que contiene el `Sub Main` procedimiento.<br /><br /> Solo un `Sub Main` procedimiento es necesario en los archivos de código fuente que se compilan en un archivo .exe. Si el código contiene más de una clase que tiene un `Sub Main` procedimiento, utilice el `-main` opción del compilador para especificar la clase que contiene el `Sub Main` procedimiento|  
|`-target:winmdobj`|Hace que el compilador cree un archivo intermedio que se puede convertir en un archivo binario (.winmd) de Windows en tiempo de ejecución. Puede consumir el archivo .winmd programas de JavaScript y C++, además de programas de lenguajes administrados.<br /><br /> El archivo intermedio se crea con una extensión .winmdobj.<br /><br /> A menos que se especifique lo contrario mediante el uso de la `-out` opción, el nombre de archivo de salida toma el nombre del primer archivo de entrada. Un `Sub Main` procedimiento no es necesario.<br /><br /> El archivo .winmdobj está diseñado para utilizarse como entrada para el <xref:Microsoft.Build.Tasks.WinMDExp> exportar herramienta para producir un archivo de metadatos (WinMD) de Windows. El archivo WinMD tiene una extensión .winmd y contiene el código de la biblioteca original y las definiciones de WinMD que JavaScript, C++ y el uso de Windows en tiempo de ejecución.|  
  
 A menos que especifique `-target:module`, `-target` hace que un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] manifiesto del ensamblado para agregarse a un archivo de salida.  
  
 Cada instancia de Vbc.exe produce, a lo sumo, un archivo de salida. Si se especifica como una opción del compilador `-out` o `-target` más de una vez, la última que procese el compilador se entra en vigor. Información sobre todos los archivos en una compilación se agrega al manifiesto. Todos los archivos, excepto los creados con resultantes `-target:module` contienen metadatos de ensamblado en el manifiesto. Use [Ildasm.exe (Desensamblador de IL)](https://msdn.microsoft.com/library/f7dy01k1) para ver los metadatos en un archivo de salida.  
  
 La forma abreviada de `-target` es `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Para establecer - tener como destino en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.   
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Modifique el valor en el **tipo de aplicación** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `in.vb`, creando `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
