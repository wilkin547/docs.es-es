---
title: Compilar desde la línea de comandos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 798baa90308c83e42b335635fb23a9983f5180fb
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739480"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilar desde la línea de comandos (Visual Basic)
Un proyecto de Visual Basic se compone de uno o varios archivos de código fuente independiente. Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.  
  
 Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. El compilador de línea de comandos está diseñado para situaciones en las que no es necesario el conjunto completo de características del IDE, por ejemplo, cuando se están utilizando o escribir en los equipos con sistema limitados memoria o espacio de almacenamiento.  
  
  Para compilar archivos de origen desde el IDE de Visual Studio, elija el **compilar** comando desde el **compilar** menú.  
  
> [!TIP]
>  Al compilar los archivos de proyecto utilizando el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando y sus modificadores en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **detalles de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle. Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos de registro de compilación](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).  
  
 Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante el uso de MSBuild. Para obtener más información, consulte [referencia de línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: Usar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Invocar al compilador de la línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema de MS-DOS o de un subdirectorio específico.  
  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Proporciona una lista de líneas de comandos de ejemplo que se pueden modificar para su propio uso.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Proporciona listas de opciones del compilador, organizadas alfabéticamente o por propósito.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Describe cómo compilar secciones concretas del código.  
  
 [Compilar y limpiar proyectos y soluciones en Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Describe cómo organizar, lo que se incluirán en diferentes compilaciones, elija las propiedades del proyecto y asegúrese de que los proyectos se compilan en el orden correcto.
