---
title: Procedimiento Main en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6de98ad4e470cd0becaf25f5a9a00c8095e44b15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="main-procedure-in-visual-basic"></a>Procedimiento Main en Visual Basic
Cada aplicación de Visual Basic debe contener un procedimiento denominado `Main`. Este procedimiento sirve como punto de partida y control general de la aplicación. Las llamadas de .NET Framework su `Main` procedimiento cuando se haya cargado la aplicación y está listo para pasar el control a él. A menos que se va a crear una aplicación de formularios Windows Forms, debe escribir el `Main` procedimiento para las aplicaciones que se ejecutan en sus propios.  
  
 `Main`contiene el código que se ejecuta primero. En `Main`, puede determinar qué forma se cargarán en primer lugar, cuando se inicia el programa, averiguar si una copia de la aplicación ya se está ejecutando en el sistema, establecer un conjunto de variables de la aplicación o abra una base de datos que requiere la aplicación.  
  
## <a name="requirements-for-the-main-procedure"></a>Requisitos para el procedimiento principal  
 Un archivo que se ejecuta en su propio (normalmente con la extensión .exe) debe contener un `Main` procedimiento. Una biblioteca (por ejemplo con la extensión .dll) no se ejecuta en su propio y no requiere un `Main` procedimiento. Los requisitos para los distintos tipos de proyectos que pueden crear son los siguientes:  
  
-   Aplicaciones de consola ejecutan por sí solas, y debe proporcionar al menos una `Main` procedimiento. .  
  
-   Aplicaciones de Windows Forms que se ejecutan por sí solas. Sin embargo, el compilador de Visual Basic genera automáticamente un `Main` procedimiento de tal aplicación y no es necesario escribir uno.  
  
-   Bibliotecas de clases no requieren un `Main` procedimiento. Esto incluye bibliotecas de controles de Windows y bibliotecas de controles Web. Las aplicaciones Web se implementan como bibliotecas de clases.  
  
## <a name="declaring-the-main-procedure"></a>Declarar el procedimiento Main  
 Hay cuatro maneras de declarar el `Main` procedimiento. Puede tomar o no argumentos y puede devolver un valor o no.  
  
> [!NOTE]
>  Si declara `Main` en una clase, debe utilizar el `Shared` palabra clave. En un módulo, `Main` no necesita ser `Shared`.  
  
-   La manera más sencilla es declarar un `Sub` procedimiento que no toma argumentos ni devolver un valor.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main`También puede devolver un `Integer` valor, que utiliza el sistema operativo como el código de salida del programa. Otros programas pueden comprobar este código examinando el valor de ERRORLEVEL de Windows. Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un `Sub` procedimiento.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   `Main`También puede tomar un `String` matriz como un argumento. Cada cadena de la matriz contiene uno de los argumentos de línea de comandos que se utiliza para invocar el programa. Puede realizar distintas acciones según sus valores.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   Puede declarar `Main` para examinar los argumentos de línea de comandos pero no devolver un código de salida, como se indica a continuación.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [String (tipo de datos)](../../../visual-basic/language-reference/data-types/string-data-type.md)
