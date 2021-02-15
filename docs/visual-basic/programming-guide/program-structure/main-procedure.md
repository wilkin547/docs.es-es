---
description: 'Más información acerca de: procedimiento principal en Visual Basic'
title: Procedimiento principal
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: b25190ef216fe4219923a27d6bbe0acff4536685
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432811"
---
# <a name="main-procedure-in-visual-basic"></a>Procedimiento Main en Visual Basic

Cada Visual Basic aplicación debe contener un procedimiento denominado `Main` . Este procedimiento sirve como punto de partida y control general de la aplicación. El .NET Framework llama `Main` al procedimiento cuando ha cargado la aplicación y está listo para pasarle el control. A menos que cree una aplicación Windows Forms, debe escribir el `Main` procedimiento para las aplicaciones que se ejecutan por sí mismas.

 `Main` contiene el código que se ejecuta en primer lugar. En `Main` , puede determinar qué formulario se va a cargar primero cuando se inicie el programa, averiguar si ya se está ejecutando una copia de la aplicación en el sistema, establecer un conjunto de variables para la aplicación o abrir una base de datos que la aplicación requiera.

## <a name="requirements-for-the-main-procedure"></a>Requisitos para el procedimiento Main

 Un archivo que se ejecuta por su cuenta (normalmente con la extensión. exe) debe contener un `Main` procedimiento. Una biblioteca (por ejemplo, con extensión. dll) no se ejecuta por sí misma y no requiere un `Main` procedimiento. Los requisitos para los diferentes tipos de proyectos que puede crear son los siguientes:

- Las aplicaciones de consola se ejecutan por sí mismas y debe proporcionar al menos un `Main` procedimiento.

- Windows Forms aplicaciones se ejecutan por sí solos. Sin embargo, el compilador de Visual Basic genera automáticamente un `Main` procedimiento en este tipo de aplicación y no es necesario escribir ninguno.

- Las bibliotecas de clases no requieren un `Main` procedimiento. Entre ellas se incluyen bibliotecas de controles de Windows y bibliotecas de controles Web. Las aplicaciones web se implementan como bibliotecas de clases.

## <a name="declaring-the-main-procedure"></a>Declarar el procedimiento Main

 Hay cuatro maneras de declarar el `Main` procedimiento. Puede tomar argumentos o no, y puede devolver un valor.

> [!NOTE]
> Si declara `Main` en una clase, debe utilizar la `Shared` palabra clave. En un módulo, no `Main` es necesario que sea `Shared` .

- La manera más sencilla consiste en declarar un `Sub` procedimiento que no tome argumentos o devuelva un valor.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` también puede devolver un `Integer` valor, que el sistema operativo usa como código de salida para el programa. Otros programas pueden probar este código examinando el valor de ERRORLEVEL de Windows. Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un `Sub` procedimiento.

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

- `Main` también puede tomar una `String` matriz como argumento. Cada cadena de la matriz contiene uno de los argumentos de línea de comandos utilizados para invocar el programa. Puede realizar diferentes acciones en función de sus valores.

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
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Estructura de un programa de Visual Basic](structure-of-a-visual-basic-program.md)
- [-main](../../reference/command-line-compiler/main.md)
- [Compartido](../../language-reference/modifiers/shared.md)
- [Instrucción Sub](../../language-reference/statements/sub-statement.md)
- [Instrucción Function](../../language-reference/statements/function-statement.md)
- [Tipo de datos Integer](../../language-reference/data-types/integer-data-type.md)
- [String (Tipo de datos)](../../language-reference/data-types/string-data-type.md)
