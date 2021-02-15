---
description: 'Más información acerca de cómo: llamar a un método de extensión (Visual Basic)'
title: Procedimiento para llamar a un método de extensión
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: ec5217526eb0cb28d172ab917df08a8bfe87fe95
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471388"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="dd23d-103">Cómo: Llamar a un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd23d-103">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="dd23d-104">Los métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="dd23d-104">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="dd23d-105">Una vez declarado y incorporado un método de extensión en el ámbito, puede llamarlo como un método de instancia del tipo que extiende.</span><span class="sxs-lookup"><span data-stu-id="dd23d-105">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="dd23d-106">Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: escribir un método de extensión](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd23d-106">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="dd23d-107">Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate` , que mostrará la instancia de la cadena que lo invoca, seguido del valor que se envía para el segundo parámetro, `punc` .</span><span class="sxs-lookup"><span data-stu-id="dd23d-107">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

<span data-ttu-id="dd23d-108">El método debe estar en el ámbito cuando se llama a.</span><span class="sxs-lookup"><span data-stu-id="dd23d-108">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="dd23d-109">Para llamar a un método de extensión</span><span class="sxs-lookup"><span data-stu-id="dd23d-109">To call an extension method</span></span>

1. <span data-ttu-id="dd23d-110">Declare una variable que tenga el tipo de datos del primer parámetro del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="dd23d-110">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="dd23d-111">Para `PrintAndPunctuate` , necesita una <xref:System.String> variable:</span><span class="sxs-lookup"><span data-stu-id="dd23d-111">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="dd23d-112">Esa variable invocará el método de extensión y su valor se enlazará al primer parámetro, `aString` .</span><span class="sxs-lookup"><span data-stu-id="dd23d-112">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="dd23d-113">Se mostrará la siguiente instrucción de llamada `Ready?` .</span><span class="sxs-lookup"><span data-stu-id="dd23d-113">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="dd23d-114">Observe que la llamada a este método de extensión tiene el aspecto de una llamada a cualquiera de los <xref:System.String> métodos de instancia que requieren un parámetro:</span><span class="sxs-lookup"><span data-stu-id="dd23d-114">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="dd23d-115">Declare otra variable de cadena y llame de nuevo al método para ver que funciona con cualquier cadena.</span><span class="sxs-lookup"><span data-stu-id="dd23d-115">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="dd23d-116">El resultado es: `or not!!!` .</span><span class="sxs-lookup"><span data-stu-id="dd23d-116">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="dd23d-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd23d-117">Example</span></span>

 <span data-ttu-id="dd23d-118">El código siguiente es un ejemplo completo de la creación y el uso de un método de extensión simple.</span><span class="sxs-lookup"><span data-stu-id="dd23d-118">The following code is a complete example of the creation and use of a simple extension method.</span></span>

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a><span data-ttu-id="dd23d-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd23d-119">See also</span></span>

- [<span data-ttu-id="dd23d-120">Procedimiento para escribir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="dd23d-120">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="dd23d-121">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="dd23d-121">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="dd23d-122">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd23d-122">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
