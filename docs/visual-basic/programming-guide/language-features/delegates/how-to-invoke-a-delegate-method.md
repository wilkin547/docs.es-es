---
title: Procedimiento para invocar un método delegado
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: f319727c007b93c7b334af0598f1b9f7c034144d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410726"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="533f6-102">Cómo: Invocar un método delegado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="533f6-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="533f6-103">En este ejemplo se muestra cómo asociar un método a un delegado y, a continuación, invocar ese método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="533f6-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="533f6-104">Crear el delegado y los procedimientos coincidentes</span><span class="sxs-lookup"><span data-stu-id="533f6-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="533f6-105">Cree un delegado denominado `MySubDelegate` .</span><span class="sxs-lookup"><span data-stu-id="533f6-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="533f6-106">Declare una clase que contenga un método con la misma firma que el delegado.</span><span class="sxs-lookup"><span data-stu-id="533f6-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="533f6-107">Defina un método que cree una instancia del delegado e invoque el método asociado al delegado llamando al `Invoke` método integrado.</span><span class="sxs-lookup"><span data-stu-id="533f6-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="533f6-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="533f6-108">See also</span></span>

- [<span data-ttu-id="533f6-109">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="533f6-109">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="533f6-110">Delegados</span><span class="sxs-lookup"><span data-stu-id="533f6-110">Delegates</span></span>](index.md)
- [<span data-ttu-id="533f6-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="533f6-111">Events</span></span>](../events/index.md)
- [<span data-ttu-id="533f6-112">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="533f6-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
