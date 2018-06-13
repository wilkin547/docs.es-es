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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0f1fc1d269801efdbf2e89d10679dc8159851f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653668"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)
Como alternativa a la compilación de programas de Visual Basic desde dentro de Visual Studio, puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).  
  
 El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones que controlan entrada y salida de archivos, ensamblados y depuración y opciones de preprocesador. Cada opción está disponible en dos formatos intercambiables: `-option` y `/option`. Esta documentación se muestra solo la `-option` formulario.  
  
 En la tabla siguiente se enumera algunas líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
|En|Usar|  
|--------|---------|  
|Compilar File.vb y crear File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilar File.vb y crear File.dll|`vbc -target:library File.vb`|  
|Compilar File.vb y crea My.exe|`vbc -out:My.exe File.vb`|  
|Compilar File.vb y crear una biblioteca y un ensamblado de referencia denominado File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilar todos los archivos de Visual Basic en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Compilar todos los archivos de Visual Basic en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Compilar todos los archivos de Visual Basic en el directorio actual al archivo algo.dll.|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando con sus opciones del compilador en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle.   
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
