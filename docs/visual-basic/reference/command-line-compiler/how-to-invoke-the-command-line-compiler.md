---
title: "Cómo: invocar al compilador de línea de comandos (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 69c95289f91f712bd3fda03a7f582d879141591a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Cómo: Invocar al compilador de la línea de comandos (Visual Basic)
Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo de MS-DOS. Si compila desde el símbolo del sistema de Windows de forma predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable. Para invalidar este comportamiento predeterminado, puede utilizar el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] símbolo o modificar la variable de entorno PATH. Ambos permiten compilar en cualquier directorio escribiendo simplemente el nombre del compilador.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Para invocar al compilador mediante el símbolo del sistema de Visual Studio  
  
1.  Abra la carpeta de programa de Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.  
  
2.  Puede usar el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] símbolo para tener acceso al compilador desde cualquier directorio en su equipo, si está instalado Visual Studio.  
  
3.  Invocar el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] símbolo del sistema.  
  
4.  En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, se abre el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Para establecer la variable de entorno PATH en el compilador para la línea de comandos de Windows  
  
1.  Utilice la característica de búsqueda de Windows para encontrar Vbc.exe en el disco local.  
  
     El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y la versión de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] instalado. Si tiene más de una versión de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] instalado, debe determinar qué versión debe utilizar (normalmente, la versión más reciente).  
  
2.  Desde el **iniciar** menú, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.  
  
3.  Haga clic en el **avanzadas** y, a continuación, haga clic en **Variables de entorno**.  
  
4.  En el **System** panel variables, seleccione **ruta** en la lista y haga clic en **editar**.  
  
5.  En el **sistema editar** cuadro de diálogo variables, mover el punto de inserción al final de la cadena en el **valor de la Variable** campo y escriba un punto y coma (;) seguido del nombre de directorio completo localizado en el paso 1.  
  
6.  Haga clic en **Aceptar** para confirmar los cambios y cerrar los cuadros de diálogo.  
  
     Después de cambiar la variable de entorno PATH, podrá ejecutar el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador en la línea de comandos de Windows desde cualquier directorio del equipo.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Para invocar al compilador mediante el símbolo del sistema de Windows  
  
1.  Desde el **iniciar** menú, haga clic en el **Accesorios** carpeta y, a continuación, abra el **símbolo del sistema de Windows**.  
  
2.  En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, se abre el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio. Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
