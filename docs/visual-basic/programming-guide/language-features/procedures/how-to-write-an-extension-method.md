---
title: 'Cómo: Escribir un método de extensión'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 697508f86ff4ff0a89150b65782121395d0fed12
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346012"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="54ad9-102">Cómo: Escribir un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54ad9-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="54ad9-103">Los métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="54ad9-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="54ad9-104">Se puede llamar al método de extensión como si fuera una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="54ad9-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="54ad9-105">Para definir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="54ad9-105">To define an extension method</span></span>

1. <span data-ttu-id="54ad9-106">Abra una aplicación Visual Basic nueva o existente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="54ad9-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="54ad9-107">En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción de importación:</span><span class="sxs-lookup"><span data-stu-id="54ad9-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="54ad9-108">Dentro de un módulo en la aplicación nueva o existente, comience la definición del método con el atributo [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) :</span><span class="sxs-lookup"><span data-stu-id="54ad9-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="54ad9-109">Tenga en cuenta que el atributo `Extension` solo se puede aplicar a un método (un `Sub` o un procedimiento `Function`) en un [módulo](../../../language-reference/statements/module-statement.md)de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="54ad9-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="54ad9-110">Si se aplica a un método en un `Class` o un `Structure`, el compilador de Visual Basic genera el error [BC36551](../../../misc/bc36551.md), "los métodos de extensión solo se pueden definir en módulos".</span><span class="sxs-lookup"><span data-stu-id="54ad9-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="54ad9-111">Declare el método de la manera habitual, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.</span><span class="sxs-lookup"><span data-stu-id="54ad9-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="54ad9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54ad9-112">Example</span></span>

<span data-ttu-id="54ad9-113">En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="54ad9-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="54ad9-114">Un segundo módulo, `Module1`, importa `StringExtensions` y llama al método.</span><span class="sxs-lookup"><span data-stu-id="54ad9-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="54ad9-115">El método de extensión debe estar en el ámbito cuando se llama a.</span><span class="sxs-lookup"><span data-stu-id="54ad9-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="54ad9-116">El método de extensión `PrintAndPunctuate` extiende la <xref:System.String> clase con un método que muestra la instancia de cadena seguida de una cadena de símbolos de puntuación enviados como parámetro.</span><span class="sxs-lookup"><span data-stu-id="54ad9-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub

End Module
```

<span data-ttu-id="54ad9-117">Observe que el método se define con dos parámetros y se llama con solo uno.</span><span class="sxs-lookup"><span data-stu-id="54ad9-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="54ad9-118">El primer parámetro, `aString`, en la definición del método se enlaza a `example`, la instancia de `String` que llama al método.</span><span class="sxs-lookup"><span data-stu-id="54ad9-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="54ad9-119">El resultado del ejemplo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="54ad9-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="54ad9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="54ad9-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="54ad9-121">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="54ad9-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="54ad9-122">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="54ad9-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="54ad9-123">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="54ad9-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="54ad9-124">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54ad9-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
