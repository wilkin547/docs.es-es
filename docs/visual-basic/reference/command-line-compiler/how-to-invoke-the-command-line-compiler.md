---
title: "C&#243;mo: Invocar al compilador de la l&#237;nea de comandos (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "línea de comandos, argumentos"
  - "argumentos de la línea de comandos"
  - "vbc.exe"
  - "compilador de Visual Basic, iniciar"
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# C&#243;mo: Invocar al compilador de la l&#237;nea de comandos (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Para invocar al compilador de la línea de comandos, escriba el nombre de su archivo ejecutable en la línea de comandos, también denominada símbolo del sistema de MS\-DOS.  Si compila en la Línea de comandos de Windows predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable.  Para anular este comportamiento predeterminado, puede utilizar el Símbolo del sistema de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] o modificar la variable de entorno PATH.  Los dos permiten compilar en cualquier directorio escribiendo simplemente el nombre del compilador.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para invocar el compilador mediante el Símbolo del sistema de Visual Studio  
  
1.  Abra la carpeta de programas Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.  
  
2.  Puede utilizar el símbolo del sistema de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] para tener acceso al compilador desde cualquier directorio del equipo, si Visual Studio está instalado.  
  
3.  Llame al Símbolo del sistema de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  
  
4.  En la línea de comandos, escriba `vbc.exe` *sourceFileName* y presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abra el Símbolo del sistema y escriba `cd SourceFiles` para cambiar a dicho directorio.  Si el directorio contiene un archivo de código fuente denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
### Para establecer la variable de entorno PATH en el compilador para la Línea de comandos de Windows  
  
1.  Utilice la característica Buscar de Windows para localizar el archivo Vbc.exe en el disco local.  
  
     El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio Windows y de la versión instalada de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  Si se han instalado varias versiones de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)], deberá determinar la versión que va a utilizar \(normalmente, la más reciente\).  
  
2.  En el menú **Inicio**, haga clic con el botón secundario en **Mi PC** y, a continuación, haga clic en **Propiedades** del menú contextual.  
  
3.  Haga clic en la ficha **Opciones avanzadas** y después en **Variables de entorno**.  
  
4.  En el panel **Variables del sistema**, seleccione **Path** de la lista y haga clic en **Modificar**.  
  
5.  En el cuadro de diálogo **Modificar la variable del sistema**, desplace el punto de inserción hasta el final de la cadena en el campo **Valor de variable** y escriba un punto y coma \(;\) seguido del nombre de directorio completo localizado en el paso 1.  
  
6.  Haga clic en **Aceptar** para aceptar los cambios y cerrar los cuadros de diálogo.  
  
     Después de cambiar la variable de entorno PATH, podrá ejecutar el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] en la Línea de comandos de Windows desde cualquier directorio del equipo.  
  
### Para invocar al compilador mediante la Línea de comandos de Windows  
  
1.  En el menú **Inicio**, haga clic en la carpeta **Accesorios** y, a continuación, abra la **Línea de comandos de Windows**.  
  
2.  En la línea de comandos, escriba `vbc.exe` *sourceFileName* y presione ENTRAR.  
  
     Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abra el Símbolo del sistema y escriba `cd SourceFiles` para cambiar a dicho directorio.  Si el directorio contiene un archivo de código fuente denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)