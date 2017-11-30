---
title: "Líneas de comandos de compilación de ejemplo (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)
Como alternativa a la compilación [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programas desde [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador de línea de comandos admite un conjunto completo de opciones que controlan los archivos de entrada y salida, los ensamblados y depuración y opciones de preprocesador. Cada opción está disponible en dos formatos intercambiables: `-``option` y `/``option`. Esta documentación se muestra solo la `/``option` formulario.  
  
 En la tabla siguiente se enumera algunas líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
|Para|Uso|  
|--------|---------|  
|Compilar File.vb y crear File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilar File.vb y crear File.dll|`vbc /target:library File.vb`|  
|Compilar File.vb y crea My.exe|`vbc /out:My.exe File.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual al archivo algo.dll.|`vbc /target:library /out:Something.dll *.vb`|  
  
 Cuando se compila desde la línea de comandos, explícitamente debe hacer referencia a Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] biblioteca en tiempo de ejecución a través de la `/reference` opción del compilador.  
  
> [!TIP]
>  Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando con sus opciones del compilador en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle. Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
