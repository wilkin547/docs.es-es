---
title: 'Cómo: Invocar al compilador de la línea de comandos (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 0b835bb5654574a5aa6f32eede1e942b11e7dcb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Cómo: Invocar al compilador de la línea de comandos (Visual Basic)
Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo de MS-DOS. Si compila desde la línea de comandos de Windows de manera predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable. Para invalidar este comportamiento predeterminado, puede usar el símbolo del sistema de Visual Studio o modificar la variable de entorno PATH. Ambos permiten compilar desde cualquier directorio escribiendo simplemente el nombre del compilador.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Para invocar al compilador mediante el símbolo del sistema de Visual Studio  
  
1.  Abra la carpeta de programas de Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.  
  
2.  Puede utilizar el símbolo del sistema de Visual Studio para tener acceso al compilador desde cualquier directorio en su equipo, si está instalado Visual Studio.  
  
3.  Invocar el símbolo del sistema de Visual Studio.  
  
4.  En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio denominado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Para establecer la variable de entorno PATH en el compilador de la línea de comandos de Windows  
  
1.  Usar la característica de búsqueda de Windows para buscar Vbc.exe en el disco local.  
  
     El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y la versión de "Instalado .NET Framework". Si tiene más de una versión de ".NET Framework" instalado, debe determinar qué versión debe utilizar (normalmente, la versión más reciente).  
  
2.  Desde el **iniciar** menú, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.  
  
3.  Haga clic en el **avanzadas** ficha y, a continuación, haga clic en **Variables de entorno**.  
  
4.  En el **System** panel variables, seleccione **ruta de acceso** en la lista y haga clic en **editar**.  
  
5.  En el **sistema editar** cuadro de diálogo Variable, mover el punto de inserción al final de la cadena en el **valor de la Variable** campo y escriba un punto y coma (;) seguido por el nombre de directorio completo se encuentra en el paso 1.  
  
6.  Haga clic en **Aceptar** para confirmar los cambios y cerrar los cuadros de diálogo.  
  
     Después de cambiar la variable de entorno PATH, podrá ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Para invocar al compilador mediante el símbolo del sistema de Windows  
  
1.  Desde el **iniciar** menú, haga clic en el **Accesorios** carpeta y, a continuación, abra el **símbolo del sistema de Windows**.  
  
2.  En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio denominado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
