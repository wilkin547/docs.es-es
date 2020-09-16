---
title: Procedimiento Llamada una función de Windows que adopta tipos sin signo
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 5b78c808de4a16060d37844ad0f17e89fa6f6d84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548083"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="6eabf-102">Cómo: Llamar a una función de Windows que adopta tipos sin signo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6eabf-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>

<span data-ttu-id="6eabf-103">Si está consumiendo una clase, un módulo o una estructura que tiene miembros de tipos enteros sin signo, puede tener acceso a estos miembros con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6eabf-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="6eabf-104">Para llamar a una función de Windows que toma un tipo sin signo</span><span class="sxs-lookup"><span data-stu-id="6eabf-104">To call a Windows function that takes an unsigned type</span></span>

1. <span data-ttu-id="6eabf-105">Use una [instrucción Declare](../../language-reference/statements/declare-statement.md) para indicar Visual Basic qué biblioteca contiene la función, cuál es su nombre en esa biblioteca, cuál es la secuencia de llamada y cómo convertir cadenas al llamarla.</span><span class="sxs-lookup"><span data-stu-id="6eabf-105">Use a [Declare Statement](../../language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>

2. <span data-ttu-id="6eabf-106">En la `Declare` instrucción, use `UInteger` , `ULong` , `UShort` o, `Byte` según corresponda, para cada parámetro con un tipo sin signo.</span><span class="sxs-lookup"><span data-stu-id="6eabf-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>

3. <span data-ttu-id="6eabf-107">Consulte la documentación de la función de Windows a la que está llamando para buscar los nombres y valores de las constantes que usa.</span><span class="sxs-lookup"><span data-stu-id="6eabf-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="6eabf-108">Muchos de ellos se definen en el archivo WinUser. h.</span><span class="sxs-lookup"><span data-stu-id="6eabf-108">Many of these are defined in the WinUser.h file.</span></span>

4. <span data-ttu-id="6eabf-109">Declare las constantes necesarias en el código.</span><span class="sxs-lookup"><span data-stu-id="6eabf-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="6eabf-110">Muchas constantes de Windows son valores sin signo de 32 bits y se deben declarar `As UInteger` .</span><span class="sxs-lookup"><span data-stu-id="6eabf-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As UInteger`.</span></span>

5. <span data-ttu-id="6eabf-111">Llame a la función de la forma normal.</span><span class="sxs-lookup"><span data-stu-id="6eabf-111">Call the function in the normal way.</span></span> <span data-ttu-id="6eabf-112">En el ejemplo siguiente se llama a la función de Windows `MessageBox` , que toma un argumento de entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="6eabf-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     <span data-ttu-id="6eabf-113">Puede probar la función `messageThroughWindows` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6eabf-113">You can test the function `messageThroughWindows` with the following code.</span></span>

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > <span data-ttu-id="6eabf-114">Los `UInteger` `ULong` tipos de datos,, `UShort` y no forman `SByte` parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede consumir un componente que los utiliza.</span><span class="sxs-lookup"><span data-stu-id="6eabf-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6eabf-115">La realización de una llamada a código no administrado, como la interfaz de programación de aplicaciones (API) de Windows, expone el código a posibles riesgos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6eabf-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6eabf-116">La llamada a la API de Windows requiere el permiso del código no administrado, lo que puede afectar a su ejecución en situaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="6eabf-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="6eabf-117">Para obtener más información, vea <xref:System.Security.Permissions.SecurityPermission> y [permisos de acceso del código](/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6eabf-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="6eabf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eabf-118">See also</span></span>

- [<span data-ttu-id="6eabf-119">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6eabf-119">Data Types</span></span>](../../language-reference/data-types/index.md)
- [<span data-ttu-id="6eabf-120">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="6eabf-120">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="6eabf-121">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="6eabf-121">UInteger Data Type</span></span>](../../language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="6eabf-122">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="6eabf-122">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)
- [<span data-ttu-id="6eabf-123">Tutorial: Llamadas a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="6eabf-123">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
