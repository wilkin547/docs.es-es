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
ms.openlocfilehash: 719ca45403ea56a655f06dbfea7c0fb7e32b34f7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046427"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilar desde la línea de comandos (Visual Basic)

Un proyecto de Visual Basic se compone de uno o varios archivos de código fuente independientes. Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.

Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. El compilador de línea de comandos está diseñado para situaciones en las que no necesita el conjunto completo de características en el IDE, por ejemplo, cuando usa o escribe en equipos con memoria de sistema o espacio de almacenamiento limitados.

Para compilar archivos de código fuente desde el IDE de Visual Studio, elija el comando compilar en el menú compilar.

> [!TIP]
> Al compilar archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el comando de **VBC** asociado y sus modificadores en la ventana de salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el nivel de detalle de la salida de la **compilación del proyecto de MSBuild** en **normal** o en un nivel más alto de detalle. Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)de registro de compilación.

Puede compilar archivos de proyecto (. vbproj) en un símbolo del sistema mediante MSBuild. Para obtener más información, vea [referencia de la línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: Usar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>En esta sección

[Cómo: Invocar al compilador de línea de comandos](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) \
Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema de MS-DOS o en un subdirectorio específico.

[Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) \
Proporciona una lista de líneas de comandos de ejemplo que puede modificar para su propio uso.

## <a name="related-sections"></a>Secciones relacionadas

[Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) \
Proporciona listas de opciones del compilador organizadas en orden alfabético o por propósito.

[Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) \
Describe cómo compilar secciones de código determinadas.

[Compilar y limpiar proyectos y soluciones en Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \
Describe cómo organizar lo que se incluirá en compilaciones diferentes, elegir las propiedades del proyecto y asegurarse de que los proyectos se compilan en el orden correcto.
