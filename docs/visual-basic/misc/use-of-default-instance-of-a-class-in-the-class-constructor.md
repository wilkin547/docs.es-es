---
title: El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cf5d3e16c43920a90b69c815f91601c6d33c845d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638383"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="54ec6-102">El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita</span><span class="sxs-lookup"><span data-stu-id="54ec6-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="54ec6-103">Se usó una instancia predeterminada de una clase en el constructor de la clase.</span><span class="sxs-lookup"><span data-stu-id="54ec6-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="54ec6-104">Esto puede derivar en una llamada recursiva infinita, también conocido como bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="54ec6-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54ec6-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="54ec6-105">To correct this error</span></span>  
  
-   <span data-ttu-id="54ec6-106">Quite la instancia predeterminada del constructor de la clase.</span><span class="sxs-lookup"><span data-stu-id="54ec6-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ec6-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="54ec6-107">See Also</span></span>  
 [<span data-ttu-id="54ec6-108">Constructores</span><span class="sxs-lookup"><span data-stu-id="54ec6-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
