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
ms.openlocfilehash: 391e16da86aa741a1b78f35d9afd95688f33c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654141"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilar desde la línea de comandos (Visual Basic)
Un proyecto de Visual Basic se compone de uno o más archivos de código fuente independiente. Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un solo archivo ejecutable que se pueden ejecutar como una aplicación.  
  
 Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. El compilador de línea de comandos está diseñado para situaciones en las que no necesitan el conjunto completo de características del IDE, por ejemplo, cuando estén usando o escribiendo en los equipos con sistema limitados memoria o espacio de almacenamiento.  
  
  Para compilar archivos de código fuente desde el IDE de Visual Studio, elija la **generar** línea de comandos desde el **generar** menú.  
  
> [!TIP]
>  Cuando compila los archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando y sus modificadores en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle. Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante MSBuild. Para obtener más información, consulte [referencia de línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: usar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>En esta sección  
 [Invocar al compilador de la línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema de MS-DOS o desde un subdirectorio específico.  
  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Proporciona una lista de líneas de comandos de ejemplo que puede modificar para su propio uso.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Se proporcionan listas de opciones del compilador, organizadas alfabéticamente o por propósito.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Describe cómo compilar secciones específicas de código.  
  
 [Compilar y limpiar proyectos y soluciones en Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Describe cómo organizar lo que se incluirán en las diferentes generaciones, elija Propiedades del proyecto y asegúrese de que los proyectos se generan en el orden correcto.
