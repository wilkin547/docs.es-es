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
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046294"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)

Como alternativa a la compilación de programas Visual Basic desde Visual Studio, puede compilar desde la línea de comandos para generar archivos ejecutables (. exe) o archivos de biblioteca de vínculos dinámicos (. dll).

El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones que controlan los archivos de entrada y salida, los ensamblados y las opciones de depuración y preprocesador. Cada opción está disponible en dos formas intercambiables: `-option` y `/option`. En esta documentación solo se `-option` muestra el formulario.

En la tabla siguiente se enumeran algunas líneas de comandos de ejemplo que puede modificar para su propio uso.

|En|Usar|
|--------|---------|
|Compile File. VB y cree File. exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Compile File. VB y cree File. dll|`vbc -target:library File.vb`|
|Compile File. VB y cree My. exe|`vbc -out:My.exe File.vb`|
|Compile File. VB y cree una biblioteca y un ensamblado de referencia denominado File. dll.|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilar todos los archivos Visual Basic en el directorio actual, con optimizaciones `DEBUG` en y el símbolo definido, produciendo archivo2. exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Compilar todos los archivos Visual Basic en el directorio actual, generando una versión de depuración de archivo2. dll sin mostrar el logotipo o las advertencias|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Compilar todos los archivos Visual Basic del directorio actual en un archivo. dll|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Al compilar un proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el comando de **VBC** asociado con sus opciones del compilador en la ventana salida. Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el nivel de detalle de la salida de la **compilación del proyecto de MSBuild** en **normal** o en un nivel más alto de detalle.

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
