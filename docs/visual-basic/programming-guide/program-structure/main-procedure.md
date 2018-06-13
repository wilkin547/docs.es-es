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
ms.openlocfilehash: 109bf94eb91292cfca700a9e456c8ab53e83d68f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652157"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="13430-102">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13430-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="13430-103">Cada aplicación de Visual Basic debe contener un procedimiento denominado `Main`.</span><span class="sxs-lookup"><span data-stu-id="13430-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="13430-104">Este procedimiento sirve como punto de partida y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="13430-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="13430-105">Las llamadas de .NET Framework su `Main` procedimiento cuando se haya cargado la aplicación y está listo para pasar el control a él.</span><span class="sxs-lookup"><span data-stu-id="13430-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="13430-106">A menos que se va a crear una aplicación de formularios Windows Forms, debe escribir el `Main` procedimiento para las aplicaciones que se ejecutan en sus propios.</span><span class="sxs-lookup"><span data-stu-id="13430-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="13430-107">`Main` contiene el código que se ejecuta primero.</span><span class="sxs-lookup"><span data-stu-id="13430-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="13430-108">En `Main`, puede determinar qué forma se cargarán en primer lugar, cuando se inicia el programa, averiguar si una copia de la aplicación ya se está ejecutando en el sistema, establecer un conjunto de variables de la aplicación o abra una base de datos que requiere la aplicación.</span><span class="sxs-lookup"><span data-stu-id="13430-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="13430-109">Requisitos para el procedimiento principal</span><span class="sxs-lookup"><span data-stu-id="13430-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="13430-110">Un archivo que se ejecuta en su propio (normalmente con la extensión .exe) debe contener un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="13430-111">Una biblioteca (por ejemplo con la extensión .dll) no se ejecuta en su propio y no requiere un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="13430-112">Los requisitos para los distintos tipos de proyectos que pueden crear son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="13430-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="13430-113">Aplicaciones de consola ejecutan por sí solas, y debe proporcionar al menos una `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="13430-114">.</span><span class="sxs-lookup"><span data-stu-id="13430-114">.</span></span>  
  
-   <span data-ttu-id="13430-115">Aplicaciones de Windows Forms que se ejecutan por sí solas.</span><span class="sxs-lookup"><span data-stu-id="13430-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="13430-116">Sin embargo, el compilador de Visual Basic genera automáticamente un `Main` procedimiento de tal aplicación y no es necesario escribir uno.</span><span class="sxs-lookup"><span data-stu-id="13430-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="13430-117">Bibliotecas de clases no requieren un `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="13430-118">Esto incluye bibliotecas de controles de Windows y bibliotecas de controles Web.</span><span class="sxs-lookup"><span data-stu-id="13430-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="13430-119">Las aplicaciones Web se implementan como bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="13430-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="13430-120">Declarar el procedimiento Main</span><span class="sxs-lookup"><span data-stu-id="13430-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="13430-121">Hay cuatro maneras de declarar el `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="13430-122">Puede tomar o no argumentos y puede devolver un valor o no.</span><span class="sxs-lookup"><span data-stu-id="13430-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13430-123">Si declara `Main` en una clase, debe utilizar el `Shared` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="13430-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="13430-124">En un módulo, `Main` no necesita ser `Shared`.</span><span class="sxs-lookup"><span data-stu-id="13430-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="13430-125">La manera más sencilla es declarar un `Sub` procedimiento que no toma argumentos ni devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="13430-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="13430-126">`Main` También puede devolver un `Integer` valor, que utiliza el sistema operativo como el código de salida del programa.</span><span class="sxs-lookup"><span data-stu-id="13430-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="13430-127">Otros programas pueden comprobar este código examinando el valor de ERRORLEVEL de Windows.</span><span class="sxs-lookup"><span data-stu-id="13430-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="13430-128">Para devolver un código de salida, debe declarar `Main` como un `Function` procedimiento en lugar de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="13430-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="13430-129">`Main` También puede tomar un `String` matriz como un argumento.</span><span class="sxs-lookup"><span data-stu-id="13430-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="13430-130">Cada cadena de la matriz contiene uno de los argumentos de línea de comandos que se utiliza para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="13430-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="13430-131">Puede realizar distintas acciones según sus valores.</span><span class="sxs-lookup"><span data-stu-id="13430-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="13430-132">Puede declarar `Main` para examinar los argumentos de línea de comandos pero no devolver un código de salida, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="13430-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13430-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="13430-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="13430-134">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13430-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="13430-135">/main</span><span class="sxs-lookup"><span data-stu-id="13430-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="13430-136">Shared</span><span class="sxs-lookup"><span data-stu-id="13430-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="13430-137">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="13430-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="13430-138">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="13430-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="13430-139">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="13430-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="13430-140">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="13430-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
