---
title: Procedimiento Invocar el compilador de línea de comandos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 67cad0df3f10ff1fa1f6a58546fe150232fe1283
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302808"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Procedimiento Invocar el compilador de línea de comandos (Visual Basic)
Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo de MS-DOS. Si compila desde la línea de comandos de Windows de forma predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable. Para invalidar este comportamiento predeterminado, puede utilizar el símbolo del sistema para desarrolladores de Visual Studio o modifique la variable de entorno PATH. Ambos permiten compilar desde cualquier directorio escribiendo simplemente el nombre del compilador.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Para invocar al compilador con el símbolo del sistema para desarrolladores para Visual Studio  
  
1. Abra la carpeta del programa de Visual Studio Tools en el grupo de programas de Microsoft Visual Studio.  
  
2. Puede utilizar el símbolo del sistema para desarrolladores para Visual Studio para tener acceso al compilador desde cualquier directorio del equipo, si está instalado Visual Studio.  
  
3. Invocar el símbolo del sistema para desarrolladores de Visual Studio.  
  
4. En la línea de comandos, escriba `vbc.exe` *sourceFileName* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, compilarlo escribiendo `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Para establecer la variable de entorno PATH en el compilador para el símbolo del sistema de Windows  
  
1. Usar la característica de Windows Search para buscar Vbc.exe en el disco local.  
  
     El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y la versión de "Instalado .NET Framework". Si tiene más de una versión de ".NET Framework" instalada, debe determinar qué versión debe utilizar (normalmente, la versión más reciente).  
  
2. Desde su **iniciar** menú, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.  
  
3. Haga clic en el **avanzadas** pestaña y, a continuación, haga clic en **Variables de entorno**.  
  
4. En el **sistema** panel variables, seleccione **ruta** en la lista y haga clic en **editar**.  
  
5. En el **sistema editar** cuadro de diálogo Variable, mover el punto de inserción al final de la cadena en el **valor de la Variable** campo y escriba un punto y coma (;) seguido del nombre de directorio completa se encuentra en el paso 1.  
  
6. Haga clic en **Aceptar** para confirmar los cambios y cerrar los cuadros de diálogo.  
  
     Después de cambiar la variable de entorno PATH, puede ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Para invocar al compilador mediante el símbolo del sistema de Windows  
  
1. Desde el **iniciar** menú, haga clic en el **Accesorios** carpeta y, a continuación, abra el **símbolo del sistema Windows**.  
  
2. En la línea de comandos, escriba `vbc.exe` *sourceFileName* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, compilarlo escribiendo `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
