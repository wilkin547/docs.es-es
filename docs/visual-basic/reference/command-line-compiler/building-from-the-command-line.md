---
title: "Compilar desde la l&#237;nea de comandos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "compilaciones [Visual Basic], línea de comandos"
  - "Compilador de Visual Basic, acerca del compilador de Visual Basic"
  - "línea de comandos [Visual Basic], compiladores"
  - "línea de comandos [Visual Basic], compilación desde"
  - "línea de comandos [Visual Basic], compilaciones"
  - "compiladores, llamar desde la línea de comandos"
  - "compilaciones desde la línea de comandos"
  - "compilar código fuente"
  - "compilador de línea de comandos, Visual Basic"
  - "línea de comandos [Visual Basic], Visual Basic"
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Compilar desde la l&#237;nea de comandos (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un proyecto de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se compone de uno o varios archivos de código fuente independientes.  Durante el proceso que se conoce por el nombre de compilación, estos archivos se reúnen en un único paquete para formar un archivo ejecutable que constituye una aplicación.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona un compilador de línea de comandos como alternativa a los programas de compilación del entorno de desarrollo integrado \(IDE\) de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Dicho compilador se ha concebido para aquellas situaciones en las que no es necesario utilizar todo el conjunto de características del IDE; por ejemplo, cuando se utiliza un equipo con una memoria del sistema limitada o con un espacio de almacenamiento escaso, o cuando se escriben programas para equipos con estas limitaciones.  
  
 Al compilar desde la línea de comandos, deberá hacer referencia explícitamente a la biblioteca en tiempo de ejecución de Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], mediante la opción de compilador `/reference`.  
  
 Para compilar archivos de código fuente desde el entorno de desarrollo integrado de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], elija el comando **Generar** en el menú **Generar**.  
  
> [!TIP]
>  Cuando se compilan los archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el comando asociado de **vbc** y los modificadores en la ventana de salida.  Para mostrar esta información, abra [Cuadro de diálogo Opciones, Proyectos y soluciones, Compilar y ejecutar](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), y establezca **Contenido de los resultados de compilación del proyecto de MSBuild** para **normal** o un mayor nivel de detalle.  Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos de registro de compilación](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md).  
  
 Puede compilar los archivos de proyecto \(.vbproj\) en un símbolo del sistema con MSBuild.  Para obtener más información, vea [Referencia de la línea de comandos](/visual-studio/msbuild/msbuild-command-line-reference) y [Tutorial: Usar MSBuild](../Topic/Walkthrough:%20Using%20MSBuild.md).  
  
## En esta sección  
 [Cómo: Invocar al compilador de la línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Explica cómo invocar al compilador de la línea de comandos en el símbolo del sistema de MS\-DOS o desde un subdirectorio en concreto.  
  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Proporciona una lista de líneas de comandos de ejemplo que puede modificar para adaptarlas a sus necesidades.  
  
## Secciones relacionadas  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Proporciona listas de opciones de compilación, organizadas por orden alfabético o por cometido.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Explica la forma de compilar secciones de código concretas.  
  
 [Compilar y limpiar proyectos y soluciones en Visual Studio](/visual-studio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Explica cómo organizar el contenido de compilaciones distintas, cómo elegir las propiedades de los proyectos y cómo asegurarse de que los proyectos se compilan en el orden correcto.