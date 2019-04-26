---
title: Procedimiento Llamar a un método de extensión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863680"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="5e43a-102">Procedimiento Llamar a un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e43a-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="5e43a-103">Métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="5e43a-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="5e43a-104">Después de un método de extensión se declaran y se incluyen en el ámbito, puede llamarlo como un método de instancia del tipo que extiende.</span><span class="sxs-lookup"><span data-stu-id="5e43a-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="5e43a-105">Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: Escribir un método de extensión](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e43a-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="5e43a-106">Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate`, que mostrará la instancia de cadena que lo invoca, seguida de cualquier valor que se envía para el segundo parámetro, `punc`.</span><span class="sxs-lookup"><span data-stu-id="5e43a-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="5e43a-107">El método debe estar en ámbito cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="5e43a-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="5e43a-108">Para llamar a un método de extensión</span><span class="sxs-lookup"><span data-stu-id="5e43a-108">To call an extension method</span></span>  
  
1. <span data-ttu-id="5e43a-109">Declare una variable que tiene el tipo de datos del primer parámetro del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="5e43a-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="5e43a-110">Para `PrintAndPunctuate`, necesita un <xref:System.String> variable:</span><span class="sxs-lookup"><span data-stu-id="5e43a-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. <span data-ttu-id="5e43a-111">Que variable invocará el método de extensión y su valor está enlazado al primer parámetro, `aString`.</span><span class="sxs-lookup"><span data-stu-id="5e43a-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="5e43a-112">Se mostrará la siguiente instrucción de llamada `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="5e43a-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="5e43a-113">Tenga en cuenta que la llamada a este método de extensión es simplemente como una llamada a cualquiera de los <xref:System.String> métodos que requieren un parámetro de instancia:</span><span class="sxs-lookup"><span data-stu-id="5e43a-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. <span data-ttu-id="5e43a-114">Declare otra variable de cadena y llame al método nuevo para comprobar que funciona con cualquier cadena.</span><span class="sxs-lookup"><span data-stu-id="5e43a-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="5e43a-115">El resultado es este tiempo: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="5e43a-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e43a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e43a-116">Example</span></span>  
 <span data-ttu-id="5e43a-117">El código siguiente es un ejemplo completo de la creación y uso de un método de extensión simple.</span><span class="sxs-lookup"><span data-stu-id="5e43a-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e43a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e43a-118">See also</span></span>

- [<span data-ttu-id="5e43a-119">Cómo: Escribir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="5e43a-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="5e43a-120">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="5e43a-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="5e43a-121">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e43a-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
