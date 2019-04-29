---
title: "'<typename>' no puede heredar del <type> '<basetypename>' porque amplía el acceso del <type> fuera del ensamblado"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: dc979a66c73fdf15a4349a003680156e0ce27ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764366"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="f68e5-102">'\<typename >' no puede heredar de \<tipo > '\<nombreDeTipoBase >' porque expande el acceso de la base de \<tipo > fuera del ensamblado</span><span class="sxs-lookup"><span data-stu-id="f68e5-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="f68e5-103">Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.</span><span class="sxs-lookup"><span data-stu-id="f68e5-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="f68e5-104">Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de un `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="f68e5-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="f68e5-105">Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.</span><span class="sxs-lookup"><span data-stu-id="f68e5-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="f68e5-106">**Identificador de error:** BC30910</span><span class="sxs-lookup"><span data-stu-id="f68e5-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f68e5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f68e5-107">To correct this error</span></span>  
  
- <span data-ttu-id="f68e5-108">Cambiar el nivel de acceso de la clase derivada o interfaz sea al menos tan restrictiva como de la clase base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="f68e5-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="f68e5-109">-o bien-</span><span class="sxs-lookup"><span data-stu-id="f68e5-109">-or-</span></span>  
  
- <span data-ttu-id="f68e5-110">Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f68e5-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="f68e5-111">No se puede heredar de una clase base más restringido o interfaz.</span><span class="sxs-lookup"><span data-stu-id="f68e5-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68e5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f68e5-112">See also</span></span>

- [<span data-ttu-id="f68e5-113">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f68e5-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="f68e5-114">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f68e5-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="f68e5-115">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f68e5-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="f68e5-116">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f68e5-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
