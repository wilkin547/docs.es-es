---
title: Líneas de comandos de compilación de ejemplo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 601f8f3a5ea86da060b2d26796b2299d87946443
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547805"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)
Como alternativa a la compilación de programas de Visual Basic desde Visual Studio, puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).  
  
 El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones que controlan la entrada y de salida de archivos, ensamblados y depuración y las opciones de preprocesador. Cada opción está disponible en dos formatos intercambiables: `-option` y `/option`. Esta documentación se muestra solo la `-option` formulario.  
  
 En la tabla siguiente se enumera algunas líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
|En|Usar|  
|--------|---------|  
|File.vb para compilar y crear File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilar File.vb y crear el archivo archivo.dll|`vbc -target:library File.vb`|  
|Compila File.vb y crea My.exe|`vbc -out:My.exe File.vb`|  
|File.vb para compilar y crear una biblioteca y un ensamblado de referencia denominado archivo.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilar todos los archivos de Visual Basic en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Compilar todos los archivos de Visual Basic en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Compilar todos los archivos de Visual Basic en el directorio actual al archivo algo.dll.|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Cuando compila un proyecto utilizando el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando con las opciones del compilador en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **detalles de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle.   
  
## <a name="see-also"></a>Vea también
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
