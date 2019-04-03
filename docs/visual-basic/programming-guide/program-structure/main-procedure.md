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
ms.openlocfilehash: 641edd2d0e0dde5f509c8fa77ccf65358fa76a31
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833678"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="f0636-102">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0636-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="f0636-103">Cada aplicación de Visual Basic debe contener un procedimiento denominado `Main`.</span><span class="sxs-lookup"><span data-stu-id="f0636-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="f0636-104">Este procedimiento sirve como punto de partida y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0636-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="f0636-105">Las llamadas de .NET Framework su `Main` procedimiento cuando se ha cargado la aplicación y está listo para pasar el control.</span><span class="sxs-lookup"><span data-stu-id="f0636-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="f0636-106">A menos que se va a crear una aplicación de Windows Forms, debe escribir el `Main` procedimiento para las aplicaciones que se ejecutan en sus propios.</span><span class="sxs-lookup"><span data-stu-id="f0636-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="f0636-107">`Main` contiene el código que se ejecuta primero.</span><span class="sxs-lookup"><span data-stu-id="f0636-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="f0636-108">En `Main`, puede determinar qué formulario se cargará en primer lugar cuando se inicia el programa, averiguar si una copia de la aplicación ya se está ejecutando en el sistema, establecer un conjunto de variables para su aplicación o abrir una base de datos que requiere la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0636-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="f0636-109">Requisitos para el procedimiento principal</span><span class="sxs-lookup"><span data-stu-id="f0636-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="f0636-110">Un archivo que se ejecuta en su propio (normalmente con la extensión .exe) debe contener un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="f0636-111">No se ejecuta en su propio de una biblioteca (por ejemplo con la extensión .dll) y no requiere un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="f0636-112">Los requisitos para los distintos tipos de proyectos que se pueden crear son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0636-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="f0636-113">Ejecutar aplicaciones de consola sus propios, y debe proporcionar al menos una `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="f0636-114">.</span><span class="sxs-lookup"><span data-stu-id="f0636-114">.</span></span>  
  
-   <span data-ttu-id="f0636-115">Las aplicaciones de Windows Forms ejecutarán solas.</span><span class="sxs-lookup"><span data-stu-id="f0636-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="f0636-116">Sin embargo, el compilador de Visual Basic genera automáticamente un `Main` procedimiento de tal una aplicación y no es necesario escribir uno.</span><span class="sxs-lookup"><span data-stu-id="f0636-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="f0636-117">Bibliotecas de clases no requieren un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="f0636-118">Estos incluyen bibliotecas de controles de Windows y bibliotecas de controles Web.</span><span class="sxs-lookup"><span data-stu-id="f0636-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="f0636-119">Las aplicaciones Web se implementan como bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="f0636-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="f0636-120">Declarar el procedimiento Main</span><span class="sxs-lookup"><span data-stu-id="f0636-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="f0636-121">Hay cuatro maneras de declarar la `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="f0636-122">Puede tomar argumentos o no, y puede devolver un valor o no.</span><span class="sxs-lookup"><span data-stu-id="f0636-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0636-123">Si declara `Main` en una clase, se debe utilizar el `Shared` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f0636-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="f0636-124">En un módulo, `Main` no necesita ser `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f0636-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="f0636-125">La manera más sencilla es declarar un `Sub` procedimiento que no toman argumentos o devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="f0636-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="f0636-126">`Main` También puede devolver un `Integer` valor, que utiliza el sistema operativo como el código de salida para el programa.</span><span class="sxs-lookup"><span data-stu-id="f0636-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="f0636-127">Otros programas pueden comprobar este código examinando el valor de ERRORLEVEL de Windows.</span><span class="sxs-lookup"><span data-stu-id="f0636-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="f0636-128">Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0636-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="f0636-129">`Main` También puede tomar un `String` matriz como argumento.</span><span class="sxs-lookup"><span data-stu-id="f0636-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="f0636-130">Cada cadena de la matriz contiene uno de los argumentos de línea de comandos que se utiliza para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="f0636-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="f0636-131">Puede realizar distintas acciones según sus valores.</span><span class="sxs-lookup"><span data-stu-id="f0636-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="f0636-132">Puede declarar `Main` para examinar los argumentos de línea de comandos pero no devolver un código de salida, de manera.</span><span class="sxs-lookup"><span data-stu-id="f0636-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0636-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0636-133">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="f0636-134">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0636-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="f0636-135">/main</span><span class="sxs-lookup"><span data-stu-id="f0636-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="f0636-136">Shared</span><span class="sxs-lookup"><span data-stu-id="f0636-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="f0636-137">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f0636-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f0636-138">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f0636-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f0636-139">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f0636-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="f0636-140">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f0636-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
