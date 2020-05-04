---
title: Líneas de comandos de compilación de ejemplo
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350853"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Líneas de comandos de compilación de ejemplo (Visual Basic)

Como alternativa a la compilación de programas de Visual Basic desde Visual Studio, se pueden realizar compilaciones desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).

El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones con las que se controlan los archivos de entrada y salida, los ensamblados y las opciones de depuración y preprocesador. Cada opción está disponible en dos formas intercambiables: `-option` y `/option`. En esta documentación solo se muestra la forma `-option`.

En la siguiente tabla se muestran algunas líneas de comandos de ejemplo que puede modificar para uso propio.

|En|Usar|
|--------|---------|
|Compilar File.vb y crear File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Compilar File.vb y crear File.dll|`vbc -target:library File.vb`|
|Compilar File.vb y crear My.exe|`vbc -out:My.exe File.vb`|
|Compilar File.vb y crear una biblioteca y un ensamblado de referencia llamado File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilar todos los archivos de Visual Basic del directorio actual, con las optimizaciones activadas y el símbolo `DEBUG` definido, creando así File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Compilar todos los archivos de Visual Basic del directorio actual, creando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Compilar todos los archivos de Visual Basic del directorio actual en un archivo Something.dll|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Cuando se compila un proyecto con el IDE de Visual Studio, se puede mostrar información sobre el comando asociado **vbc** con sus opciones de compilador en la ventana salida. Para ver esta información, abra el cuadro de diálogo [Opciones - Proyectos y soluciones - Compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) y establezca **Detalles de la salida de la compilación del proyecto de MSBuild** en **Normal** o en un nivel de detalle más alto.

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
