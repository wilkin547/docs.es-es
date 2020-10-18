---
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160950"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a><span data-ttu-id="ee438-102">BC30298: el constructor ' \<name> ' no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="ee438-102">BC30298: Constructor '\<name>' cannot call itself</span></span>

<span data-ttu-id="ee438-103">Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ee438-103">A `Sub New` procedure in a class or structure calls itself.</span></span>

 <span data-ttu-id="ee438-104">El propósito de un constructor es inicializar una instancia de una clase o estructura cuando se crea por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ee438-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="ee438-105">Una clase o estructura puede tener varios constructores, siempre que todos tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="ee438-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="ee438-106">Se permite a un constructor llamar a otro constructor para realizar su funcionalidad además de la suya propia.</span><span class="sxs-lookup"><span data-stu-id="ee438-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="ee438-107">Pero no tiene sentido que un constructor se llame a sí mismo y, de hecho, daría como resultado una recursividad infinita si se permitiera.</span><span class="sxs-lookup"><span data-stu-id="ee438-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>

 <span data-ttu-id="ee438-108">**Identificador de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="ee438-108">**Error ID:** BC30298</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ee438-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ee438-109">To correct this error</span></span>

1. <span data-ttu-id="ee438-110">Compruebe la lista de parámetros del constructor al que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="ee438-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="ee438-111">Debe ser diferente del constructor que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ee438-111">It should be different from that of the constructor making the call.</span></span>

2. <span data-ttu-id="ee438-112">Si no desea llamar a un constructor diferente, quite la llamada por `Sub New` completo.</span><span class="sxs-lookup"><span data-stu-id="ee438-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee438-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee438-113">See also</span></span>

- [<span data-ttu-id="ee438-114">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="ee438-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
