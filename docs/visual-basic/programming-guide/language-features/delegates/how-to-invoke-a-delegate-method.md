---
description: 'Más información acerca de cómo: invocar un método delegado (Visual Basic)'
title: Procedimiento para invocar un método delegado
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c5c20048969f2fef16b8b7f65e84a094a3f1cf9f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434477"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="a118f-103">Cómo: Invocar un método delegado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a118f-103">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="a118f-104">En este ejemplo se muestra cómo asociar un método a un delegado y, a continuación, invocar ese método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="a118f-104">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="a118f-105">Crear el delegado y los procedimientos coincidentes</span><span class="sxs-lookup"><span data-stu-id="a118f-105">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="a118f-106">Cree un delegado denominado `MySubDelegate` .</span><span class="sxs-lookup"><span data-stu-id="a118f-106">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="a118f-107">Declare una clase que contenga un método con la misma firma que el delegado.</span><span class="sxs-lookup"><span data-stu-id="a118f-107">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="a118f-108">Defina un método que cree una instancia del delegado e invoque el método asociado al delegado llamando al `Invoke` método integrado.</span><span class="sxs-lookup"><span data-stu-id="a118f-108">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="a118f-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a118f-109">See also</span></span>

- [<span data-ttu-id="a118f-110">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="a118f-110">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="a118f-111">Delegados</span><span class="sxs-lookup"><span data-stu-id="a118f-111">Delegates</span></span>](index.md)
- [<span data-ttu-id="a118f-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="a118f-112">Events</span></span>](../events/index.md)
- [<span data-ttu-id="a118f-113">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="a118f-113">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
