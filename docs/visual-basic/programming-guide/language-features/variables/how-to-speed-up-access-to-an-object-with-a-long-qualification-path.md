---
title: Procedimiento Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 827d7d1574e85a30ec2724f7739f6c3a08dbd975
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519729"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="73f74-102">Procedimiento Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73f74-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="73f74-103">Si frecuentemente tiene acceso a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar su código no repite la ruta de acceso de calificación.</span><span class="sxs-lookup"><span data-stu-id="73f74-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="73f74-104">Hay dos maneras de evitar la repetición de la ruta de acceso de calificación.</span><span class="sxs-lookup"><span data-stu-id="73f74-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="73f74-105">El objeto se puede asignar a una variable, o puede usarla en un `With`... `End With` bloque.</span><span class="sxs-lookup"><span data-stu-id="73f74-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="73f74-106">Para acelerar el acceso a un objeto muy calificado asignándolo a una variable</span><span class="sxs-lookup"><span data-stu-id="73f74-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="73f74-107">Declare una variable del tipo del objeto que tiene acceso con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="73f74-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="73f74-108">Especifique la ruta de acceso de calificación en la parte de la inicialización de la declaración.</span><span class="sxs-lookup"><span data-stu-id="73f74-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="73f74-109">Use la variable para tener acceso a los miembros del objeto.</span><span class="sxs-lookup"><span data-stu-id="73f74-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="73f74-110">Para acelerar el acceso a un objeto muy calificado mediante el uso de r con... Bloque End With</span><span class="sxs-lookup"><span data-stu-id="73f74-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="73f74-111">Coloque la ruta de acceso de calificación en una `With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="73f74-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="73f74-112">Obtener acceso a los miembros del objeto dentro de la `With` bloquear, antes del `End With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="73f74-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="73f74-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f74-113">See also</span></span>
- [<span data-ttu-id="73f74-114">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="73f74-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="73f74-115">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73f74-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
