---
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: ef20f74055a07071ef9634973c6852ac58c3143c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824725"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="7e1ea-102">Constructor '\<nombre >' no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="7e1ea-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="7e1ea-103">Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="7e1ea-104">Es el propósito de un constructor inicializar una instancia de una clase o estructura cuando sea primera creado.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="7e1ea-105">Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="7e1ea-106">Se permite un constructor para llamar a otro constructor para llevar a cabo su funcionalidad además de su propio.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="7e1ea-107">Pero no tiene sentido que un constructor llame a sí mismo y de hecho el resultado sería una recursividad infinita si lo permite.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="7e1ea-108">**Identificador de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="7e1ea-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e1ea-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7e1ea-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="7e1ea-110">Compruebe la lista de parámetros del constructor que se llama.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="7e1ea-111">Debe ser diferente de la que realiza la llamada de constructor.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="7e1ea-112">Si no piensa llamar a un constructor diferente, quite el `Sub New` llamar por completo.</span><span class="sxs-lookup"><span data-stu-id="7e1ea-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1ea-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e1ea-113">See also</span></span>

- [<span data-ttu-id="7e1ea-114">Duración del objeto: ¿Cómo se crean y destruyen objetos</span><span class="sxs-lookup"><span data-stu-id="7e1ea-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
