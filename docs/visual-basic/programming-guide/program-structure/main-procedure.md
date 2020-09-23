---
title: Procedimiento principal
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: d6708ee13963aaae43a73b159032f64f0fffac10
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072215"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="78894-102">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78894-102">Main Procedure in Visual Basic</span></span>

<span data-ttu-id="78894-103">Cada Visual Basic aplicación debe contener un procedimiento denominado `Main` .</span><span class="sxs-lookup"><span data-stu-id="78894-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="78894-104">Este procedimiento sirve como punto de partida y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="78894-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="78894-105">El .NET Framework llama `Main` al procedimiento cuando ha cargado la aplicación y está listo para pasarle el control.</span><span class="sxs-lookup"><span data-stu-id="78894-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="78894-106">A menos que cree una aplicación Windows Forms, debe escribir el `Main` procedimiento para las aplicaciones que se ejecutan por sí mismas.</span><span class="sxs-lookup"><span data-stu-id="78894-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="78894-107">`Main` contiene el código que se ejecuta en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="78894-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="78894-108">En `Main` , puede determinar qué formulario se va a cargar primero cuando se inicie el programa, averiguar si ya se está ejecutando una copia de la aplicación en el sistema, establecer un conjunto de variables para la aplicación o abrir una base de datos que la aplicación requiera.</span><span class="sxs-lookup"><span data-stu-id="78894-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="78894-109">Requisitos para el procedimiento Main</span><span class="sxs-lookup"><span data-stu-id="78894-109">Requirements for the Main Procedure</span></span>

 <span data-ttu-id="78894-110">Un archivo que se ejecuta por su cuenta (normalmente con la extensión. exe) debe contener un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="78894-111">Una biblioteca (por ejemplo, con extensión. dll) no se ejecuta por sí misma y no requiere un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="78894-112">Los requisitos para los diferentes tipos de proyectos que puede crear son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="78894-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="78894-113">Las aplicaciones de consola se ejecutan por sí mismas y debe proporcionar al menos un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="78894-114">Windows Forms aplicaciones se ejecutan por sí solos.</span><span class="sxs-lookup"><span data-stu-id="78894-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="78894-115">Sin embargo, el compilador de Visual Basic genera automáticamente un `Main` procedimiento en este tipo de aplicación y no es necesario escribir ninguno.</span><span class="sxs-lookup"><span data-stu-id="78894-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="78894-116">Las bibliotecas de clases no requieren un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="78894-117">Entre ellas se incluyen bibliotecas de controles de Windows y bibliotecas de controles Web.</span><span class="sxs-lookup"><span data-stu-id="78894-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="78894-118">Las aplicaciones web se implementan como bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="78894-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="78894-119">Declarar el procedimiento Main</span><span class="sxs-lookup"><span data-stu-id="78894-119">Declaring the Main Procedure</span></span>

 <span data-ttu-id="78894-120">Hay cuatro maneras de declarar el `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="78894-121">Puede tomar argumentos o no, y puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="78894-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="78894-122">Si declara `Main` en una clase, debe utilizar la `Shared` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="78894-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="78894-123">En un módulo, no `Main` es necesario que sea `Shared` .</span><span class="sxs-lookup"><span data-stu-id="78894-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="78894-124">La manera más sencilla consiste en declarar un `Sub` procedimiento que no tome argumentos o devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="78894-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="78894-125">`Main` también puede devolver un `Integer` valor, que el sistema operativo usa como código de salida para el programa.</span><span class="sxs-lookup"><span data-stu-id="78894-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="78894-126">Otros programas pueden probar este código examinando el valor de ERRORLEVEL de Windows.</span><span class="sxs-lookup"><span data-stu-id="78894-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="78894-127">Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78894-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

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

- <span data-ttu-id="78894-128">`Main` también puede tomar una `String` matriz como argumento.</span><span class="sxs-lookup"><span data-stu-id="78894-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="78894-129">Cada cadena de la matriz contiene uno de los argumentos de línea de comandos utilizados para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="78894-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="78894-130">Puede realizar diferentes acciones en función de sus valores.</span><span class="sxs-lookup"><span data-stu-id="78894-130">You can take different actions depending on their values.</span></span>

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

- <span data-ttu-id="78894-131">Puede declarar `Main` para examinar los argumentos de la línea de comandos, pero no devolver un código de salida, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="78894-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

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
  
## <a name="see-also"></a><span data-ttu-id="78894-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="78894-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="78894-133">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78894-133">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="78894-134">-main</span><span class="sxs-lookup"><span data-stu-id="78894-134">-main</span></span>](../../reference/command-line-compiler/main.md)
- [<span data-ttu-id="78894-135">Compartido</span><span class="sxs-lookup"><span data-stu-id="78894-135">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="78894-136">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="78894-136">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="78894-137">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="78894-137">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="78894-138">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="78894-138">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="78894-139">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="78894-139">String Data Type</span></span>](../../language-reference/data-types/string-data-type.md)
