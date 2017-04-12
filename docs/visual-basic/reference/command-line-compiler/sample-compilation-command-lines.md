---
title: "Muestra líneas de comandos de compilación (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 918787b3377f2e5a636a6b098046ac2f455efcdd
ms.lasthandoff: 03/13/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)
Como alternativa a la compilación [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programas desde [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador de línea de comandos admite un conjunto completo de opciones que controlan la depuración, ensamblados y los archivos de entrada y salidos y las opciones de preprocesador. Cada opción está disponible en dos formatos intercambiables: `-``option` y `/``option`. Esta documentación se muestra únicamente el `/``option` formulario.  
  
 La tabla siguiente enumeran algunas líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
|Para|Uso|  
|--------|---------|  
|Compilar el archivo archivo.vb y crear File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilar el archivo archivo.vb y crear File.dll|`vbc /target:library File.vb`|  
|Compilar el archivo archivo.vb y crea My.exe|`vbc /out:My.exe File.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Todos los compilar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos en el directorio actual en el archivo algo.dll.|`vbc /target:library /out:Something.dll *.vb`|  
  
 Al compilar desde la línea de comandos, debe hacer explícitamente referencia Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] biblioteca de tiempo de ejecución a través de la `/reference` opción del compilador.  
  
> [!TIP]
>  Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el asociado **vbc** comando con las opciones del compilador en la ventana de salida. Para mostrar esta información, abra la [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle. Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
