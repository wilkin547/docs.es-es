---
title: Procedimiento Main en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 1c76e3ade0b383727c3241fdaf5ae44b677559c8
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775692"
---
# <a name="main-procedure-in-visual-basic"></a>Procedimiento Main en Visual Basic
Cada Visual Basic aplicación debe contener un procedimiento denominado `Main`. Este procedimiento sirve como punto de partida y control general de la aplicación. El .NET Framework llama a su `Main` procedimiento cuando haya cargado la aplicación y esté listo para pasarle el control. A menos que cree una aplicación Windows Forms, debe escribir el procedimiento de `Main` para las aplicaciones que se ejecutan por sí mismas.

 `Main` contiene el código que se ejecuta en primer lugar. En `Main`, puede determinar qué formulario se va a cargar primero cuando se inicie el programa, averiguar si ya se está ejecutando una copia de la aplicación en el sistema, establecer un conjunto de variables para la aplicación o abrir una base de datos que la aplicación requiera.

## <a name="requirements-for-the-main-procedure"></a>Requisitos para el procedimiento Main
 Un archivo que se ejecuta por su cuenta (normalmente con la extensión. exe) debe contener un procedimiento `Main`. Una biblioteca (por ejemplo, con extensión. dll) no se ejecuta por sí misma y no requiere un procedimiento `Main`. Los requisitos para los diferentes tipos de proyectos que puede crear son los siguientes:

- Las aplicaciones de consola se ejecutan por sí mismas, por lo que debe proporcionar al menos un procedimiento `Main`.

- Windows Forms aplicaciones se ejecutan por sí solos. Sin embargo, el compilador de Visual Basic genera automáticamente un procedimiento de `Main` en este tipo de aplicación y no es necesario escribir ninguno.

- Las bibliotecas de clases no requieren un procedimiento `Main`. Entre ellas se incluyen bibliotecas de controles de Windows y bibliotecas de controles Web. Las aplicaciones web se implementan como bibliotecas de clases.

## <a name="declaring-the-main-procedure"></a>Declarar el procedimiento Main
 Hay cuatro maneras de declarar el procedimiento `Main`. Puede tomar argumentos o no, y puede devolver un valor.

> [!NOTE]
> Si declara `Main` en una clase, debe utilizar la palabra clave `Shared`. En un módulo, `Main` no tiene que ser `Shared`.

- La manera más sencilla consiste en declarar un procedimiento `Sub` que no tome argumentos o devuelva un valor.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` también puede devolver un valor `Integer`, que el sistema operativo usa como código de salida para el programa. Otros programas pueden probar este código examinando el valor de ERRORLEVEL de Windows. Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un procedimiento `Sub`.

    ```vb
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

- `Main` también puede tomar una matriz de `String` como argumento. Cada cadena de la matriz contiene uno de los argumentos de línea de comandos utilizados para invocar el programa. Puede realizar diferentes acciones en función de sus valores.

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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

- Puede declarar `Main` para examinar los argumentos de la línea de comandos, pero no devolver un código de salida, como se indica a continuación.

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [String (tipo de datos)](../../../visual-basic/language-reference/data-types/string-data-type.md)
