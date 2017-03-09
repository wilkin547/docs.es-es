---
title: "L&#237;neas de comandos de compilaci&#243;n de ejemplo (Visual Basic) | Microsoft Docs"
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
  - "línea de comandos, compiladores"
  - "compilación, línea de comandos"
  - "compiladores de línea de comandos"
  - "compilación de código fuente, desde la línea de comandos"
  - "Compilador de Visual Basic, líneas de comandos de muestra"
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# L&#237;neas de comandos de compilaci&#243;n de ejemplo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Como alternativa a la compilación de programas de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] desde [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], existe la posibilidad de compilar desde la línea de comandos para generar archivos ejecutables \(.exe\) o archivos de biblioteca de vínculos dinámicos \(.dll\).  
  
 El compilador de la línea de comandos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] admite un conjunto completo de opciones que controlan los archivos de entrada y de salida, los ensamblados y las opciones de depuración y del preprocesador.  Estas opciones están disponibles en dos formatos intercambiables: `-``option`y `/``option`.  En esta documentación sólo se muestra el formato `/``option`.  
  
 En la tabla que aparece a continuación se muestra una lista de líneas de comandos de ejemplo que puede modificar para adaptarlas a sus necesidades.  
  
|Para|Uso|  
|----------|---------|  
|Compilar el archivo Archivo.vb y crear el archivo Archivo.exe|`vbc /reference:Microsoft.VisualBasic.dll Archivo.vb`|  
|Compilar el archivo Archivo.vb y crear el archivo Archivo.dll|`vbc /target:library Archivo.vb`|  
|Compilar el archivo Archivo.vb y crear el archivo Mi.exe|`vbc /out:Mi.exe Archivo.vb`|  
|Compilar todos los archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] del directorio actual, con optimizaciones activadas y el símbolo `DEBUG` definido, para generar el archivo Archivo2.exe|`vbc /define:DEBUG=1 /optimize /out:Archivo2.exe *.vb`|  
|Compilar todos los archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] del directorio actual, para generar una versión depurada del archivo Archivo2.dll sin mostrar el logotipo ni advertencias.|`vbc /target:library /out:Archivo2.dll /nowarn /nologo /debug *.vb`|  
|Compilar todos los archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] del directorio actual en el archivo Algo.dll.|`vbc /target:library /out:Algo.dll *.vb`|  
  
 Al compilar desde la línea de comandos, deberá hacer referencia explícitamente a la biblioteca en tiempo de ejecución de Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], mediante la opción de compilador `/reference`.  
  
> [!TIP]
>  Cuando se compila un proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el comando asociado de **vbc** con las opciones del compilador en la ventana de salida.  Para mostrar esta información, abra [Cuadro de diálogo Opciones, Proyectos y soluciones, Compilar y ejecutar](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), y establezca **Contenido de los resultados de compilación del proyecto de MSBuild** para **normal** o un mayor nivel de detalle.  Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos de registro de compilación](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md).  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)