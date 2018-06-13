---
title: Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 069de813a0426230e19cddf14c3b83d40a602a41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589001"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="5aed3-102">Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="5aed3-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="5aed3-103">A `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="5aed3-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="5aed3-104">El propósito de un constructor es inicializar una instancia de una clase o estructura cuando es el primero creado.</span><span class="sxs-lookup"><span data-stu-id="5aed3-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="5aed3-105">Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="5aed3-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="5aed3-106">Un constructor tiene permiso para llamar a otro constructor para realizar su funcionalidad además de su propio.</span><span class="sxs-lookup"><span data-stu-id="5aed3-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="5aed3-107">Pero carece de significado para un constructor llame a sí mismo y, de hecho produciría una recursividad infinita si permite.</span><span class="sxs-lookup"><span data-stu-id="5aed3-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="5aed3-108">**Id. de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="5aed3-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5aed3-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5aed3-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="5aed3-110">Compruebe la lista de parámetros del constructor que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="5aed3-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="5aed3-111">Debe ser diferente de la del constructor que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="5aed3-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="5aed3-112">Si no desea llamar a un constructor diferente, quite el `Sub New` llamar completamente.</span><span class="sxs-lookup"><span data-stu-id="5aed3-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aed3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aed3-113">See Also</span></span>  
 [<span data-ttu-id="5aed3-114">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="5aed3-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
