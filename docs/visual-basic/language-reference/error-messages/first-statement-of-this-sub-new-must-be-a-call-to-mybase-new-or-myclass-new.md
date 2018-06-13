---
title: La primera instrucción de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (ningún Constructor accesible sin parámetros)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589465"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="f4b1e-102">La primera instrucción de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (ningún Constructor accesible sin parámetros)</span><span class="sxs-lookup"><span data-stu-id="f4b1e-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="f4b1e-103">La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' porque clase base\<basename >' de '\<derivedname >' no tiene un 'Sub New' accesible que se pueda llamar sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="f4b1e-104">En una clase derivada, cada constructor debe llamar a un constructor de clase base (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="f4b1e-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="f4b1e-105">Si la clase base tiene un constructor sin parámetros accesible para las clases derivadas, `MyBase.New` puede llamarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="f4b1e-106">De lo contrario, debe llamar a un constructor de clase base con parámetros y no puede hacerlo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="f4b1e-107">En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor de la clase derivada que realiza un constructor de clase base llamada.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="f4b1e-108">**Id. de error:** BC30148</span><span class="sxs-lookup"><span data-stu-id="f4b1e-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4b1e-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f4b1e-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f4b1e-110">Llamar a `MyBase.New` indicando los parámetros necesarios, o llamar a un constructor del mismo nivel que realiza una llamada de este tipo.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="f4b1e-111">Por ejemplo, si la clase base tiene un constructor que se declara como `Public Sub New(ByVal index as Integer)`, la primera instrucción de la clase derivada podría ser el constructor de clase `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b1e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4b1e-112">See Also</span></span>  
 [<span data-ttu-id="f4b1e-113">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="f4b1e-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
