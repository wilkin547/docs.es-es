---
description: 'Más información acerca de cómo: escribir un método de extensión (Visual Basic)'
title: Procedimiento para escribir un método de extensión
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 4c5d88976e55288ccb350ab82d459db0a23f468e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476194"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="12bfe-103">Cómo: Escribir un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12bfe-103">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="12bfe-104">Los métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="12bfe-104">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="12bfe-105">Se puede llamar al método de extensión como si fuera una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="12bfe-105">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="12bfe-106">Para definir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="12bfe-106">To define an extension method</span></span>

1. <span data-ttu-id="12bfe-107">Abra una aplicación Visual Basic nueva o existente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="12bfe-107">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="12bfe-108">En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción de importación:</span><span class="sxs-lookup"><span data-stu-id="12bfe-108">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="12bfe-109">Dentro de un módulo en la aplicación nueva o existente, comience la definición del método con el [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) atributo:</span><span class="sxs-lookup"><span data-stu-id="12bfe-109">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="12bfe-110">Tenga en cuenta que el `Extension` atributo solo se puede aplicar a un método (un `Sub` `Function` procedimiento o) en un [módulo](../../../language-reference/statements/module-statement.md)de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12bfe-110">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="12bfe-111">Si se aplica a un método en `Class` o `Structure` , el compilador Visual Basic genera el error [BC36551](../../../misc/bc36551.md), "los métodos de extensión solo se pueden definir en módulos".</span><span class="sxs-lookup"><span data-stu-id="12bfe-111">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="12bfe-112">Declare el método de la manera habitual, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.</span><span class="sxs-lookup"><span data-stu-id="12bfe-112">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="12bfe-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12bfe-113">Example</span></span>

<span data-ttu-id="12bfe-114">En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions` .</span><span class="sxs-lookup"><span data-stu-id="12bfe-114">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="12bfe-115">Un segundo módulo, `Module1` , importa `StringExtensions` y llama al método.</span><span class="sxs-lookup"><span data-stu-id="12bfe-115">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="12bfe-116">El método de extensión debe estar en el ámbito cuando se llama a.</span><span class="sxs-lookup"><span data-stu-id="12bfe-116">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="12bfe-117">El método de extensión `PrintAndPunctuate` extiende la <xref:System.String> clase con un método que muestra la instancia de cadena seguida de una cadena de símbolos de puntuación enviados como parámetro.</span><span class="sxs-lookup"><span data-stu-id="12bfe-117">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

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

<span data-ttu-id="12bfe-118">Observe que el método se define con dos parámetros y se llama con solo uno.</span><span class="sxs-lookup"><span data-stu-id="12bfe-118">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="12bfe-119">El primer parámetro, `aString` , en la definición del método, se enlaza a `example` , la instancia de `String` que llama al método.</span><span class="sxs-lookup"><span data-stu-id="12bfe-119">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="12bfe-120">El resultado del ejemplo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="12bfe-120">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="12bfe-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12bfe-121">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="12bfe-122">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="12bfe-122">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="12bfe-123">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="12bfe-123">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="12bfe-124">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="12bfe-124">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="12bfe-125">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12bfe-125">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
