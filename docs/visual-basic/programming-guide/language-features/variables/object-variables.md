---
title: Variables de objeto en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="3bdf0-102">Variables de objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bdf0-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="3bdf0-103">Además de almacenar valores directamente, una variable puede hacer referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="3bdf0-104">Asignar un objeto a una variable por las mismas razones que se asigne cualquier valor a una variable:</span><span class="sxs-lookup"><span data-stu-id="3bdf0-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="3bdf0-105">Un nombre de variable suele ser más corto y más fácil de recordar que la ruta de acceso completa de métodos y propiedades necesarios para tener acceso el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="3bdf0-106">Uso de una variable que hace referencia a un objeto es más eficaz que acceso repetidamente el propio objeto a través de las propiedades o métodos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="3bdf0-107">Puede cambiar una variable para hacer referencia a otros objetos mientras se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="3bdf0-108">El código es más corto</span><span class="sxs-lookup"><span data-stu-id="3bdf0-108">Making Code Shorter</span></span>  
 <span data-ttu-id="3bdf0-109">Puede usar variables de objeto para acortar el código que tiene que escribir.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="3bdf0-110">En el ejemplo siguiente se utiliza la ruta de acceso completa de métodos y propiedades para tener acceso a un <xref:System.Windows.Forms.Control> objeto.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="3bdf0-111">Puede reducir este código y acelerar la ejecución, si usa una variable de objeto para el control.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="3bdf0-112">Debe declarar la variable de objeto con la clase específica que se va a asignar a él (`Control` en este caso).</span><span class="sxs-lookup"><span data-stu-id="3bdf0-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="3bdf0-113">Una vez que se asigna un objeto a la variable, podrá tratarla exactamente el mismo tal y como se trata el objeto al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="3bdf0-114">Puede establecer o recuperar las propiedades del objeto o utilizar cualquiera de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="3bdf0-115">En el ejemplo siguiente se utiliza una variable de objeto para simplificar el código en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="3bdf0-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bdf0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bdf0-116">See Also</span></span>  
 [<span data-ttu-id="3bdf0-117">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="3bdf0-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="3bdf0-118">Acelerar el acceso a un objeto con una ruta de acceso de calificación larga</span><span class="sxs-lookup"><span data-stu-id="3bdf0-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="3bdf0-119">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="3bdf0-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="3bdf0-120">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="3bdf0-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="3bdf0-121">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="3bdf0-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
