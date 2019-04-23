---
title: Procedimiento Escribir un método de extensión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 00d62d275f7afc06e066a375dc1ffcd74b23c9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313767"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="a9c2f-102">Procedimiento Escribir un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9c2f-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="a9c2f-103">Métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="a9c2f-104">El método de extensión puede llamarse como si fuera una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="a9c2f-105">Para definir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="a9c2f-105">To define an extension method</span></span>  
  
1. <span data-ttu-id="a9c2f-106">Abra una aplicación nueva o existente de Visual Basic en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2. <span data-ttu-id="a9c2f-107">En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción import:</span><span class="sxs-lookup"><span data-stu-id="a9c2f-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3. <span data-ttu-id="a9c2f-108">Dentro de un módulo en la aplicación nueva o existente, comience la definición de método con el atributo de extensión:</span><span class="sxs-lookup"><span data-stu-id="a9c2f-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4. <span data-ttu-id="a9c2f-109">Declare el método de la manera normal, excepto que el tipo del primer parámetro debe ser el tipo de datos que desea extender.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="a9c2f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9c2f-110">Example</span></span>  
 <span data-ttu-id="a9c2f-111">En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="a9c2f-112">Un segundo módulo `Module1`, importa `StringExtensions` y llama al método.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="a9c2f-113">El método de extensión debe estar en ámbito cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="a9c2f-114">Método de extensión `PrintAndPunctuate` amplía la <xref:System.String> clase con un método que muestra la instancia de la cadena seguida de una cadena de signos de puntuación enviados como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
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
  
 <span data-ttu-id="a9c2f-115">Tenga en cuenta que el método se define con dos parámetros y llama a con solo uno.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="a9c2f-116">El primer parámetro, `aString`, en el método de definición se enlaza a `example`, la instancia de `String` que llama al método.</span><span class="sxs-lookup"><span data-stu-id="a9c2f-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="a9c2f-117">El resultado del ejemplo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9c2f-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="a9c2f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9c2f-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="a9c2f-119">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="a9c2f-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="a9c2f-120">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a9c2f-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="a9c2f-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="a9c2f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a9c2f-122">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9c2f-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
