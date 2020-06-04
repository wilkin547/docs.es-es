---
title: Procedimiento para hacer referencia a la instancia actual de un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410430"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="d0f27-102">Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0f27-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="d0f27-103">La *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="d0f27-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="d0f27-104">La `Me` palabra clave se usa para hacer referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="d0f27-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="d0f27-105">Para hacer referencia a la instancia actual</span><span class="sxs-lookup"><span data-stu-id="d0f27-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="d0f27-106">Use la `Me` palabra clave donde normalmente usaría el nombre de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="d0f27-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="d0f27-107">Aunque se `Me` comporta como una variable de objeto, no se puede declarar ni asignar nada.</span><span class="sxs-lookup"><span data-stu-id="d0f27-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="d0f27-108">`Me`siempre hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="d0f27-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f27-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0f27-109">See also</span></span>

- [<span data-ttu-id="d0f27-110">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="d0f27-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="d0f27-111">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="d0f27-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="d0f27-112">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="d0f27-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
