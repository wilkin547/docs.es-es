---
title: El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 14c498bf3067415f8de2afaeaaa57cf3f28ae857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022459"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="40629-102">El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita</span><span class="sxs-lookup"><span data-stu-id="40629-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="40629-103">Se usó una instancia predeterminada de una clase en el constructor de la clase.</span><span class="sxs-lookup"><span data-stu-id="40629-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="40629-104">Esto puede derivar en una llamada recursiva infinita, también conocido como bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="40629-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40629-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="40629-105">To correct this error</span></span>  
  
- <span data-ttu-id="40629-106">Quite la instancia predeterminada del constructor de la clase.</span><span class="sxs-lookup"><span data-stu-id="40629-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40629-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="40629-107">See also</span></span>

- [<span data-ttu-id="40629-108">Constructores</span><span class="sxs-lookup"><span data-stu-id="40629-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
