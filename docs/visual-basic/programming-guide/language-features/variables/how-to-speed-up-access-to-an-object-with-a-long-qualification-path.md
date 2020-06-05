---
title: Procedimiento para acelerar el acceso a un objeto con una ruta de acceso de calificación larga
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: fe93e7bac2a21f1060d1f93765eb35e1ad0c7eb0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410417"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="7446f-102">Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7446f-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="7446f-103">Si tiene acceso a menudo a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar el código sin repetir la ruta de acceso de la calificación.</span><span class="sxs-lookup"><span data-stu-id="7446f-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="7446f-104">Hay dos maneras de evitar repetir la ruta de acceso de la calificación.</span><span class="sxs-lookup"><span data-stu-id="7446f-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="7446f-105">Puede asignar el objeto a una variable o puede usarlo en un `With` bloque... `End With` .</span><span class="sxs-lookup"><span data-stu-id="7446f-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="7446f-106">Para acelerar el acceso a un objeto muy calificado mediante su asignación a una variable</span><span class="sxs-lookup"><span data-stu-id="7446f-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="7446f-107">Declare una variable del tipo del objeto al que tiene acceso con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="7446f-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="7446f-108">Especifique la ruta de acceso de calificación en la parte de inicialización de la declaración.</span><span class="sxs-lookup"><span data-stu-id="7446f-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="7446f-109">Use la variable para obtener acceso a los miembros del objeto.</span><span class="sxs-lookup"><span data-stu-id="7446f-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="7446f-110">Para acelerar el acceso a un objeto muy calificado mediante un con... Terminar con bloque</span><span class="sxs-lookup"><span data-stu-id="7446f-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="7446f-111">Coloque la ruta de acceso de la calificación en una `With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7446f-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="7446f-112">Obtenga acceso a los miembros del objeto dentro del `With` bloque, antes de la `End With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7446f-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="7446f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7446f-113">See also</span></span>

- [<span data-ttu-id="7446f-114">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="7446f-114">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="7446f-115">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="7446f-115">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
