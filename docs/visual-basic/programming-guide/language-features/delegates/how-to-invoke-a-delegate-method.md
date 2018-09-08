---
title: 'Cómo: Invocar un método delegado (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c50a32d300aaf52efe0c55cef69d5793a98305ac
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204611"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="4a8d5-102">Cómo: Invocar un método delegado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a8d5-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="4a8d5-103">En este ejemplo se muestra cómo asociar un método con un delegado y, a continuación, se invoca ese método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="4a8d5-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="4a8d5-104">Crear el delegado y los procedimientos correspondientes</span><span class="sxs-lookup"><span data-stu-id="4a8d5-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="4a8d5-105">Cree un delegado denominado `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="4a8d5-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="4a8d5-106">Declare una clase que contiene un método con la misma firma que el delegado.</span><span class="sxs-lookup"><span data-stu-id="4a8d5-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="4a8d5-107">Defina un método que crea una instancia del delegado e invoca el método asociado con el delegado mediante una llamada a la integrada `Invoke` método.</span><span class="sxs-lookup"><span data-stu-id="4a8d5-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4a8d5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a8d5-108">See also</span></span>

- [<span data-ttu-id="4a8d5-109">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4a8d5-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
- [<span data-ttu-id="4a8d5-110">Delegados</span><span class="sxs-lookup"><span data-stu-id="4a8d5-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
- [<span data-ttu-id="4a8d5-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="4a8d5-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
- [<span data-ttu-id="4a8d5-112">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="4a8d5-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
