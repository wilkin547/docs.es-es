---
title: "Procedimiento Main en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Main"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "main (función)"
  - "Main (método) [Visual Basic]"
  - "Main (procedimiento)"
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Procedimiento Main en Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Todas las aplicaciones de Visual Basic deben contener un procedimiento denominado `Main`.  Este procedimiento sirve como punto de partida y control general de la aplicación.  .NET Framework llama al procedimiento `Main` cuando ha cargado la aplicación y está listo para pasarle el control.  A menos que vaya a crear una aplicación de Windows Forms, debe escribir el procedimiento `Main` para las aplicaciones que se ejecutan por sí solas.  
  
 `Main` contiene el código que se ejecuta primero.  En `Main`, se puede especificar qué formulario se cargará primero al iniciar el programa, se puede saber si se está ejecutando una copia de la aplicación en el sistema, establecer un conjunto de variables para la aplicación o abrir una base de datos que la aplicación requiera.  
  
## Requisitos para el procedimiento Main  
 Un archivo que se ejecuta por sí solo \(normalmente con la extensión .exe\) debe contener un procedimiento `Main`.  Una biblioteca \(por ejemplo con la extensión .dll\) no se ejecuta por sí sola y no requiere un procedimiento `Main`.  Los requisitos para los diferentes tipos de proyectos que se pueden crear son los siguientes:  
  
-   Aplicaciones de consola que se ejecutan por sí solas; se debe proporcionar al menos un procedimiento `Main`.  .  
  
-   Aplicaciones de formularios Windows Forms que se ejecutan por sí solas.  Sin embargo, el compilador de Visual Basic genera automáticamente un procedimiento `Main` en este tipo de aplicación y no es necesario escribir uno.  
  
-   Las bibliotecas de clases no requieren un procedimiento `Main`.  Entre ellas se incluyen las bibliotecas de controles de Windows y las bibliotecas de controles Web.  Las aplicaciones Web se implementan como bibliotecas de clases.  
  
## Declarar el procedimiento Main  
 Hay cuatro formas de declarar el procedimiento `Main`.  Puede tomar o no argumentos y puede devolver o no un valor.  
  
> [!NOTE]
>  Si se declara `Main` en una clase, hay que utilizar la palabra clave `Shared`.  En un módulo, `Main` no necesita ser `Shared`.  
  
-   La manera más simple es declarar un procedimiento `Sub` que no toma los argumentos ni devuelve un valor.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main` también puede devolver un valor `Integer`, que el sistema operativo utiliza como código de salida del programa.  Otros programas pueden comprobar este código examinando el valor de ERRORLEVEL de Windows.  Para devolver un código de salida, se debe declarar `Main` como un procedimiento `Function`, no como un procedimiento `Sub`.  
  
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
  
-   `Main` también puede tomar como argumento una matriz de tipo `String`.  Cada cadena de la matriz contiene uno de los argumentos de línea de comandos que se utiliza para invocar el programa.  Puede tomar acciones distintas en función de sus valores.  
  
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
  
-   Se puede declarar `Main` para examinar los argumentos de línea de comandos pero no devolver un código de salida, de la manera siguiente.  
  
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
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>   
 <xref:System.Array.Length%2A>   
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [Versión de Visual Basic del programa Hola a todos](http://msdn.microsoft.com/es-es/9d030b60-e148-4366-a462-69532f02294c)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [String \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/string-data-type.md)