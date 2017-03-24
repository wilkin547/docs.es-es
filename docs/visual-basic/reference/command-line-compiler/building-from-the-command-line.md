---
title: "Compilar desde la línea de comandos (Visual Basic) | Documentos de Microsoft"
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
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers, invoking from command line
- command-line builds
- compiling source code
- command-line compilers, Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 49f84c221e18457ab46534ca46da7c4764a8ee40
ms.lasthandoff: 03/13/2017

---
# <a name="building-from-the-command-line-visual-basic"></a>Compilar desde la línea de comandos (Visual Basic)
Un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proyecto está formado por uno o más archivos de código fuente independiente. Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] el entorno de desarrollo integrado (IDE). El compilador de línea de comandos está diseñado para situaciones en las que no es necesario el conjunto completo de características del IDE, por ejemplo, si está utilizando o escribiendo para equipos con espacio de almacenamiento o memoria de sistema limitados.  
  
 Al compilar desde la línea de comandos, debe hacer explícitamente referencia Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] biblioteca de tiempo de ejecución a través de la `/reference` opción del compilador.  
  
 Para compilar archivos de código fuente desde el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] IDE, elija la **crear** comando desde el **crear** menú.  
  
> [!TIP]
>  Al generar archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el asociado **vbc** comando y sus modificadores en la ventana de salida. Para mostrar esta información, abra la [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle. Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante MSBuild. Para obtener más información, consulte [referencia de línea de comandos](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: usar MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).  
  
## <a name="in-this-section"></a>En esta sección  
 [Invocar al compilador de la línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema de MS-DOS o desde un subdirectorio específico.  
  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Proporciona una lista de líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Proporciona listas de opciones del compilador, organizadas alfabéticamente o por propósito.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Describe cómo compilar secciones concretas del código.  
  
 [Compilar y limpiar proyectos y soluciones en Visual Studio](https://docs.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Describe cómo organizar lo que se incluirá en distintas generaciones, elija Propiedades del proyecto y garantizar que los proyectos se generen en el orden correcto.
