---
title: Compilar desde la línea de comandos
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
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344790"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilar desde la línea de comandos (Visual Basic)

Un proyecto de Visual Basic se compone de uno o varios archivos de código fuente independientes. Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.

Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. El compilador de línea de comandos está diseñado para situaciones en las que no se necesita el conjunto completo de características en el IDE; por ejemplo, cuando se usan equipos con memoria de sistema o espacio de almacenamiento limitados, o se escribe para estos equipos.

Para compilar los archivos de código fuente desde el IDE de Visual Studio, elija el comando **Compilar** en el menú **Compilar**.

> [!TIP]
> Al compilar archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información acerca del comando **vbc** asociado y sus modificadores en la ventana de resultados. Para mostrar esta información, abra el [cuadro de diálogo Opciones, Proyectos y soluciones, Compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) y, posteriormente, establezca el **nivel de detalle del resultado de la compilación del proyecto de MSBuild** en **Normal** o en un nivel más alto de detalle. Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos de registro de compilación](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).

Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante MSBuild. Para más información, consulte [Referencia de la línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: Usar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>En esta sección

[Cómo: Invocación del compilador de la línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) \
Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema MS-DOS o en un subdirectorio específico.

[Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) \
Proporciona una lista de líneas de comandos de ejemplo que puede modificar para su propio uso.

## <a name="related-sections"></a>Secciones relacionadas

[Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) \
Proporciona listas de opciones del compilador organizadas en orden alfabético o por finalidad.

[Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) \
Describe cómo compilar secciones de código determinadas.

[Compilar y limpiar proyectos y soluciones en Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \
Describe cómo organizar lo que se incluirá en compilaciones diferentes, elegir las propiedades del proyecto y asegurarse de que los proyectos se compilan en el orden correcto.
