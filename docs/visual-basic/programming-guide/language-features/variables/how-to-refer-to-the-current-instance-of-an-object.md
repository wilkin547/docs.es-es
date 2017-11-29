---
title: "Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="115c9-102">Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="115c9-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="115c9-103">El *instancia actual* de un objeto es la instancia en la que se esté ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="115c9-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="115c9-104">Usa el `Me` palabra clave para hacer referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="115c9-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="115c9-105">Para hacer referencia a la instancia actual</span><span class="sxs-lookup"><span data-stu-id="115c9-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="115c9-106">Utilice la `Me` palabra clave donde utilizaría normalmente el nombre de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="115c9-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="115c9-107">Aunque `Me` se comporta como un objeto variable, no puede declararla ni asignarle nada.</span><span class="sxs-lookup"><span data-stu-id="115c9-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="115c9-108">`Me`siempre hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="115c9-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115c9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="115c9-109">See Also</span></span>  
 [<span data-ttu-id="115c9-110">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="115c9-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="115c9-111">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="115c9-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="115c9-112">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="115c9-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
