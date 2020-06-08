---
title: Procedimiento Invocación del compilador de la línea de comandos
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 6def53d4a2d15dda3e3ac43abe35b3100f456fe9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408613"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Procedimiento Invocación del compilador de la línea de comandos (Visual Basic)

Para invocar el compilador de la línea de comandos, puede escribir el nombre del archivo ejecutable correspondiente en la línea de comandos, también conocida como símbolo del sistema de MS-DOS. Si se compila desde el símbolo del sistema de Windows predeterminado, es necesario escribir la ruta de acceso completa al archivo ejecutable. Para invalidar este comportamiento predeterminado, se puede usar el Símbolo del sistema para desarrolladores de Visual Studio, o bien modificar la variable de entorno PATH. Ambos métodos permiten compilar desde cualquier directorio, simplemente escribiendo el nombre del compilador.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Para invocar el compilador usando el Símbolo del sistema para desarrolladores de Visual Studio

1. Abra la carpeta del programa Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.

2. Si Visual Studio está instalado, se puede usar el Símbolo del sistema para desarrolladores de Visual Studio para acceder al compilador desde cualquier directorio del equipo.

3. Invoque el Símbolo del sistema para desarrolladores de Visual Studio.

4. En la línea de comandos, escriba `vbc.exe` *sourceFileName* y presione Entrar.

    Por ejemplo, si tiene almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio. Si el directorio contuviera un archivo de código fuente denominado `Source.vb`, se podría compilar escribiendo `vbc.exe Source.vb`.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Para establecer la variable de entorno PATH en el compilador del símbolo del sistema de Windows

1. Use la característica Windows Search para encontrar Vbc.exe en el disco local.

    El nombre exacto del directorio donde está el compilador depende de la ubicación del directorio de Windows y de la versión de .NET Framework que haya instalada. Si hay más de una versión de .NET Framework instalada, hay que determinar cuál usar (normalmente, la última).

2. En el menú **Inicio**, haga clic con el botón derecho en **Mi PC** y, después, haga clic en **Propiedades** en el menú contextual.

3. Haga clic en la pestaña **Avanzadas** y, después, en **Variables de entorno**.

4. En el panel **Variables del sistema**, seleccione **Path** de la lista y haga clic en **Editar**.

5. En el cuadro de diálogo **Editar la variable del sistema**, mueva el punto de inserción al final de la cadena en el campo **Valor de la variable** y escriba un punto y coma (;) seguido del nombre de directorio completo del paso 1.

6. Haga clic en **Aceptar** para confirmar las modificaciones y cierre los cuadros de diálogo.

     Después de cambiar la variable de entorno PATH, puede ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Para invocar el compilador con el símbolo del sistema de Windows

1. En el menú **Inicio**, haga clic en la carpeta **Accesorios** y, después, abra **Símbolo del sistema de Windows**.

2. En la línea de comandos, escriba `vbc.exe`*sourceFileName* y presione Entrar.

     Por ejemplo, si tiene almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio. Si el directorio contuviera un archivo de código fuente denominado `Source.vb`, se podría compilar escribiendo `vbc.exe Source.vb`.

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md)
