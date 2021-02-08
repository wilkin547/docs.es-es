---
description: "Más información sobre: BC30148: la primera instrucción de este ' Sub New ' debe ser una llamada a ' MyBase. New ' o ' MyClass. New ' (no hay ningún constructor accesible sin parámetros)"
title: La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' (constructor no accesible sin parámetros)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 4138055f3634c060c7416947966b1cf18fb03b94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796228"
---
# <a name="bc30148-first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="7fdfe-103">BC30148: la primera instrucción de este ' Sub New ' debe ser una llamada a ' MyBase. New ' o ' MyClass. New ' (no hay ningún constructor accesible sin parámetros)</span><span class="sxs-lookup"><span data-stu-id="7fdfe-103">BC30148: First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>

<span data-ttu-id="7fdfe-104">La primera instrucción de este ' Sub New ' debe ser una llamada a ' MyBase. New ' o ' MyClass. New ' porque la clase base ' \<basename> ' de ' \<derivedname> ' no tiene un ' Sub New ' accesible al que se pueda llamar sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="7fdfe-104">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>

 <span data-ttu-id="7fdfe-105">En una clase derivada, cada constructor debe llamar a un constructor de clase base ( `MyBase.New` ).</span><span class="sxs-lookup"><span data-stu-id="7fdfe-105">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="7fdfe-106">Si la clase base tiene un constructor sin parámetros que es accesible para las clases derivadas, `MyBase.New` se puede llamar a de forma automática.</span><span class="sxs-lookup"><span data-stu-id="7fdfe-106">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="7fdfe-107">Si no es así, se debe llamar a un constructor de clase base con parámetros y no se puede hacer de forma automática.</span><span class="sxs-lookup"><span data-stu-id="7fdfe-107">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="7fdfe-108">En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor de la clase derivada que realiza una llamada a un constructor de clase base.</span><span class="sxs-lookup"><span data-stu-id="7fdfe-108">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>

 <span data-ttu-id="7fdfe-109">**Identificador de error:** BC30148</span><span class="sxs-lookup"><span data-stu-id="7fdfe-109">**Error ID:** BC30148</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7fdfe-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7fdfe-110">To correct this error</span></span>

- <span data-ttu-id="7fdfe-111">Llame a para `MyBase.New` proporcionar los parámetros necesarios o llame a un constructor del mismo nivel que realice esta llamada.</span><span class="sxs-lookup"><span data-stu-id="7fdfe-111">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>

     <span data-ttu-id="7fdfe-112">Por ejemplo, si la clase base tiene un constructor declarado como `Public Sub New(ByVal index as Integer)` , la primera instrucción del constructor de la clase derivada podría ser `MyBase.New(100)` .</span><span class="sxs-lookup"><span data-stu-id="7fdfe-112">For example, if the base class has a constructor that's declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fdfe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fdfe-113">See also</span></span>

- [<span data-ttu-id="7fdfe-114">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="7fdfe-114">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
