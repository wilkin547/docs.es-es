---
title: Procedimiento Hacer referencia a la instancia actual de un objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 3c44748798d5ed554fc9fbded9c3a4d981a66d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769036"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="0d0b3-102">Procedimiento Hacer referencia a la instancia actual de un objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d0b3-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="0d0b3-103">El *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="0d0b3-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="0d0b3-104">Usa el `Me` palabra clave para hacer referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="0d0b3-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="0d0b3-105">Para hacer referencia a la instancia actual</span><span class="sxs-lookup"><span data-stu-id="0d0b3-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="0d0b3-106">Utilice el `Me` palabra clave donde utilizaría normalmente el nombre de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="0d0b3-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="0d0b3-107">Aunque `Me` se comporta como un objeto variable, no puede declararla ni asignarle nada.</span><span class="sxs-lookup"><span data-stu-id="0d0b3-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="0d0b3-108">`Me` siempre se hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="0d0b3-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0b3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d0b3-109">See also</span></span>

- [<span data-ttu-id="0d0b3-110">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="0d0b3-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="0d0b3-111">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="0d0b3-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="0d0b3-112">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="0d0b3-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
