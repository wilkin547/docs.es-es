---
title: "Constructor &#39; &lt;nombre&gt;&#39; no se puede llamar a sí mismo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="6c416-102">Constructor &#39; &lt;nombre&gt;&#39; no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="6c416-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="6c416-103">A `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="6c416-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="6c416-104">El propósito de un constructor es inicializar una instancia de una clase o estructura cuando es el primero creado.</span><span class="sxs-lookup"><span data-stu-id="6c416-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="6c416-105">Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="6c416-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="6c416-106">Un constructor tiene permiso para llamar a otro constructor para realizar su funcionalidad además de su propio.</span><span class="sxs-lookup"><span data-stu-id="6c416-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="6c416-107">Pero carece de significado para un constructor llame a sí mismo y, de hecho produciría una recursividad infinita si permite.</span><span class="sxs-lookup"><span data-stu-id="6c416-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="6c416-108">**Id. de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="6c416-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6c416-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6c416-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="6c416-110">Compruebe la lista de parámetros del constructor que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="6c416-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="6c416-111">Debe ser diferente de la del constructor que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="6c416-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="6c416-112">Si no desea llamar a un constructor diferente, quite el `Sub New` llamar completamente.</span><span class="sxs-lookup"><span data-stu-id="6c416-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c416-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c416-113">See Also</span></span>  
 [<span data-ttu-id="6c416-114">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="6c416-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
