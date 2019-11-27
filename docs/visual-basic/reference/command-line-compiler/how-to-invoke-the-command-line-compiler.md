---
title: 'Cómo: Invocar al compilador de la línea de comandos'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344256"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Cómo: Invocar al compilador de la línea de comandos (Visual Basic)

Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo del sistema de MS-DOS. Si compila desde el símbolo del sistema de Windows predeterminado, debe escribir la ruta de acceso completa al archivo ejecutable. Para invalidar este comportamiento predeterminado, puede usar el Símbolo del sistema para desarrolladores para Visual Studio o modificar la variable de entorno PATH. Ambos permiten compilar desde cualquier directorio simplemente escribiendo el nombre del compilador.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Para invocar el compilador mediante el Símbolo del sistema para desarrolladores para Visual Studio

1. Abra la carpeta programa de Visual Studio Tools dentro del grupo de programas Microsoft Visual Studio.

2. Puede usar el Símbolo del sistema para desarrolladores de Visual Studio para tener acceso al compilador desde cualquier directorio del equipo, si Visual Studio está instalado.

3. Invoque el Símbolo del sistema para desarrolladores para Visual Studio.

4. En la línea de comandos, escriba `vbc.exe` *sourceFileName* y, a continuación, presione Entrar.

    Por ejemplo, si ha almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de código fuente denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Para establecer la variable de entorno PATH en el compilador para el símbolo del sistema de Windows

1. Use la característica búsqueda de Windows para encontrar VBC. exe en el disco local.

    El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y de la versión del ".NET Framework" instalada. Si tiene más de una versión de ".NET Framework" instalada, debe determinar qué versión usar (normalmente la última versión).

2. En el menú **Inicio** , haga clic con el botón secundario en **mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.

3. Haga clic en el **Opciones avanzadas** y a continuación, haga clic en **Variables de entorno**.

4. En el panel variables **del sistema** , seleccione **ruta de acceso** en la lista y haga clic en **Editar**.

5. En el cuadro de diálogo **Editar variable del sistema** , mueva el punto de inserción hasta el final de la cadena en el campo de valor de la **variable** y escriba un punto y coma (;) seguido por el nombre de directorio completo que se encuentra en el paso 1.

6. Haga clic en **Aceptar** para confirmar las modificaciones y cerrar los cuadros de diálogo.

     Después de cambiar la variable de entorno PATH, puede ejecutar el compilador Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Para invocar el compilador mediante el símbolo del sistema de Windows

1. En el menú **Inicio** , haga clic en la carpeta **accesorios** y, a continuación, abra el símbolo del **sistema de Windows**.

2. En la línea de comandos, escriba `vbc.exe`*sourceFileName* y, a continuación, presione Entrar.

     Por ejemplo, si ha almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de código fuente denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
