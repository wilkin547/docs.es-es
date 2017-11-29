---
title: "Cómo: Llamar a un método de extensión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="e2730-102">Cómo: Llamar a un método de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2730-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="e2730-103">Métodos de extensión permiten agregar métodos a una clase existente.</span><span class="sxs-lookup"><span data-stu-id="e2730-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="e2730-104">Después de que se declara un método de extensión y se incluyen en el ámbito, se puede llamar como un método de instancia del tipo que extiende.</span><span class="sxs-lookup"><span data-stu-id="e2730-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="e2730-105">Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: escribir un método de extensión](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="e2730-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="e2730-106">Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate`, que mostrará la instancia de cadena que lo invoca, seguida de cualquier valor se envía para el segundo parámetro, `punc`.</span><span class="sxs-lookup"><span data-stu-id="e2730-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="e2730-107">El método debe estar en ámbito cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="e2730-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="e2730-108">Para llamar a un método de extensión</span><span class="sxs-lookup"><span data-stu-id="e2730-108">To call an extension method</span></span>  
  
1.  <span data-ttu-id="e2730-109">Declare una variable que tiene el tipo de datos del primer parámetro del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="e2730-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="e2730-110">Para `PrintAndPunctuate`, necesita un <xref:System.String> variable:</span><span class="sxs-lookup"><span data-stu-id="e2730-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  <span data-ttu-id="e2730-111">Que la variable va a invocar el método de extensión y su valor se enlaza al primer parámetro, `aString`.</span><span class="sxs-lookup"><span data-stu-id="e2730-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="e2730-112">Se mostrará la siguiente instrucción que realiza la llamada `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="e2730-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="e2730-113">Tenga en cuenta que la llamada a este método de extensión se parece simplemente como una llamada a cualquiera de los <xref:System.String> métodos que requieren un parámetro de instancia:</span><span class="sxs-lookup"><span data-stu-id="e2730-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  <span data-ttu-id="e2730-114">Declare otra variable de cadena y llame al método nuevo para comprobar que funciona con cualquier cadena.</span><span class="sxs-lookup"><span data-stu-id="e2730-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="e2730-115">El resultado es este tiempo: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="e2730-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2730-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2730-116">Example</span></span>  
 <span data-ttu-id="e2730-117">El código siguiente es un ejemplo completo de la creación y uso de un método de extensión simple.</span><span class="sxs-lookup"><span data-stu-id="e2730-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2730-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2730-118">See Also</span></span>  
 [<span data-ttu-id="e2730-119">Escribir un método de extensión</span><span class="sxs-lookup"><span data-stu-id="e2730-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)  
 [<span data-ttu-id="e2730-120">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="e2730-120">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="e2730-121">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2730-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
