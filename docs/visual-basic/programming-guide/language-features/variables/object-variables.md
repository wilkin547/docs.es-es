---
title: Variables de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410340"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="5e542-102">Variables de objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e542-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="5e542-103">Además de almacenar los valores directamente, una variable puede hacer referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="5e542-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="5e542-104">Un objeto se asigna a una variable por las mismas razones por las que se asigna cualquier valor a una variable:</span><span class="sxs-lookup"><span data-stu-id="5e542-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="5e542-105">Un nombre de variable suele ser más corto y más fácil de recordar que la ruta de acceso completa de los métodos y las propiedades necesarios para acceder al propio objeto.</span><span class="sxs-lookup"><span data-stu-id="5e542-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="5e542-106">El uso de una variable que hace referencia a un objeto es más eficaz que el acceso repetido al propio objeto a través de los métodos o propiedades necesarios.</span><span class="sxs-lookup"><span data-stu-id="5e542-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="5e542-107">Puede cambiar una variable para hacer referencia a otros objetos mientras se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="5e542-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="5e542-108">Crear código más corto</span><span class="sxs-lookup"><span data-stu-id="5e542-108">Making Code Shorter</span></span>

<span data-ttu-id="5e542-109">Puede usar variables de objeto para acortar el código que tiene que escribir.</span><span class="sxs-lookup"><span data-stu-id="5e542-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="5e542-110">En el ejemplo siguiente se usa la ruta de acceso completa de los métodos y propiedades para tener acceso a un <xref:System.Windows.Forms.Control> objeto.</span><span class="sxs-lookup"><span data-stu-id="5e542-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="5e542-111">Puede acortar este código y acelerar la ejecución si usa una variable de objeto para el control.</span><span class="sxs-lookup"><span data-stu-id="5e542-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="5e542-112">Debe declarar la variable de objeto con la clase específica que desee asignar a ella ( `Control` en este caso,).</span><span class="sxs-lookup"><span data-stu-id="5e542-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="5e542-113">Una vez que se asigna un objeto a la variable, se puede tratar exactamente igual que el objeto al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5e542-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="5e542-114">Puede establecer o recuperar las propiedades del objeto o usar cualquiera de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="5e542-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="5e542-115">En el ejemplo siguiente se usa una variable de objeto para simplificar el código del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5e542-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="5e542-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e542-116">See also</span></span>

- [<span data-ttu-id="5e542-117">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="5e542-117">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="5e542-118">Procedimiento para acelerar el acceso a un objeto con una ruta de acceso de calificación larga</span><span class="sxs-lookup"><span data-stu-id="5e542-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="5e542-119">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="5e542-119">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="5e542-120">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="5e542-120">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="5e542-121">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="5e542-121">Object Variable Values</span></span>](object-variable-values.md)
