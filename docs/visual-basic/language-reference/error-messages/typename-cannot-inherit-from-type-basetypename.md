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
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838955"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="66982-102">'\<typename >' no puede heredar de \<tipo > '\<nombreDeTipoBase >' porque expande el acceso de la base de \<tipo > fuera del ensamblado</span><span class="sxs-lookup"><span data-stu-id="66982-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="66982-103">Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.</span><span class="sxs-lookup"><span data-stu-id="66982-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="66982-104">Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de un `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="66982-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="66982-105">Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.</span><span class="sxs-lookup"><span data-stu-id="66982-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="66982-106">**Identificador de error:** BC30910</span><span class="sxs-lookup"><span data-stu-id="66982-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66982-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="66982-107">To correct this error</span></span>  
  
-   <span data-ttu-id="66982-108">Cambiar el nivel de acceso de la clase derivada o interfaz sea al menos tan restrictiva como de la clase base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="66982-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="66982-109">-o bien-</span><span class="sxs-lookup"><span data-stu-id="66982-109">-or-</span></span>  
  
-   <span data-ttu-id="66982-110">Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción.</span><span class="sxs-lookup"><span data-stu-id="66982-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="66982-111">No se puede heredar de una clase base más restringido o interfaz.</span><span class="sxs-lookup"><span data-stu-id="66982-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66982-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="66982-112">See also</span></span>

- [<span data-ttu-id="66982-113">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="66982-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="66982-114">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="66982-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="66982-115">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="66982-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="66982-116">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66982-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
