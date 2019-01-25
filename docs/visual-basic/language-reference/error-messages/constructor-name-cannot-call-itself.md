---
title: Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 4a02277893147716098a3dcc327e221e0775d476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662730"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="8c13a-102">Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="8c13a-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="8c13a-103">Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="8c13a-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="8c13a-104">Es el propósito de un constructor inicializar una instancia de una clase o estructura cuando sea primera creado.</span><span class="sxs-lookup"><span data-stu-id="8c13a-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="8c13a-105">Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="8c13a-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="8c13a-106">Se permite un constructor para llamar a otro constructor para llevar a cabo su funcionalidad además de su propio.</span><span class="sxs-lookup"><span data-stu-id="8c13a-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="8c13a-107">Pero no tiene sentido que un constructor llame a sí mismo y de hecho el resultado sería una recursividad infinita si lo permite.</span><span class="sxs-lookup"><span data-stu-id="8c13a-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="8c13a-108">**Identificador de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="8c13a-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c13a-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8c13a-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="8c13a-110">Compruebe la lista de parámetros del constructor que se llama.</span><span class="sxs-lookup"><span data-stu-id="8c13a-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="8c13a-111">Debe ser diferente de la que realiza la llamada de constructor.</span><span class="sxs-lookup"><span data-stu-id="8c13a-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="8c13a-112">Si no piensa llamar a un constructor diferente, quite el `Sub New` llamar por completo.</span><span class="sxs-lookup"><span data-stu-id="8c13a-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c13a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c13a-113">See also</span></span>
- [<span data-ttu-id="8c13a-114">Duración del objeto: ¿Cómo se crean y destruyen objetos</span><span class="sxs-lookup"><span data-stu-id="8c13a-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
