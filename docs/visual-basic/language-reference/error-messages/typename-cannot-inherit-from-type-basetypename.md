---
title: "'<typename>' no puede heredar del <type> '<basetypename>' porque amplía el acceso del <type> fuera del ensamblado"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5c019f9d74b11e48aa05a1480b9449fa28488b43
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161847"
---
# <a name="bc30910-typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="ab00c-102">BC30910: ' \<typename> ' no puede heredar de \<type> ' \<basetypename> ' porque expande el acceso de la base \<type> fuera del ensamblado</span><span class="sxs-lookup"><span data-stu-id="ab00c-102">BC30910: '\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="ab00c-103">Una clase o interfaz hereda de una clase base o una interfaz, pero tiene un nivel de acceso menos restrictivo.</span><span class="sxs-lookup"><span data-stu-id="ab00c-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>

 <span data-ttu-id="ab00c-104">Por ejemplo, una `Public` interfaz hereda de una `Friend` interfaz o una `Protected` clase hereda de una `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="ab00c-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="ab00c-105">Esto expone la clase base o la interfaz para obtener acceso más allá del nivel previsto.</span><span class="sxs-lookup"><span data-stu-id="ab00c-105">This exposes the base class or interface to access beyond the intended level.</span></span>

 <span data-ttu-id="ab00c-106">**Identificador de error:** BC30910</span><span class="sxs-lookup"><span data-stu-id="ab00c-106">**Error ID:** BC30910</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ab00c-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ab00c-107">To correct this error</span></span>

- <span data-ttu-id="ab00c-108">Cambie el nivel de acceso de la clase o la interfaz derivada para que sea al menos tan restrictiva como la de la clase base o la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ab00c-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>

     <span data-ttu-id="ab00c-109">o bien</span><span class="sxs-lookup"><span data-stu-id="ab00c-109">-or-</span></span>

- <span data-ttu-id="ab00c-110">Si necesita el nivel de acceso menos restrictivo, quite la `Inherits` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ab00c-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="ab00c-111">No se puede heredar de una interfaz o clase base más restringida.</span><span class="sxs-lookup"><span data-stu-id="ab00c-111">You cannot inherit from a more restricted base class or interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab00c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab00c-112">See also</span></span>

- [<span data-ttu-id="ab00c-113">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="ab00c-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="ab00c-114">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="ab00c-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="ab00c-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="ab00c-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="ab00c-116">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab00c-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
