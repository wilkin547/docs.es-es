---
description: "Más información sobre: BC30298: el constructor ' <name> ' no se puede llamar a sí mismo"
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 486495eb822e3e3008382232091fe3923851f97c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796722"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a><span data-ttu-id="60a63-103">BC30298: el constructor ' \<name> ' no se puede llamar a sí mismo</span><span class="sxs-lookup"><span data-stu-id="60a63-103">BC30298: Constructor '\<name>' cannot call itself</span></span>

<span data-ttu-id="60a63-104">Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="60a63-104">A `Sub New` procedure in a class or structure calls itself.</span></span>

 <span data-ttu-id="60a63-105">El propósito de un constructor es inicializar una instancia de una clase o estructura cuando se crea por primera vez.</span><span class="sxs-lookup"><span data-stu-id="60a63-105">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="60a63-106">Una clase o estructura puede tener varios constructores, siempre que todos tengan listas de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="60a63-106">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="60a63-107">Se permite a un constructor llamar a otro constructor para realizar su funcionalidad además de la suya propia.</span><span class="sxs-lookup"><span data-stu-id="60a63-107">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="60a63-108">Pero no tiene sentido que un constructor se llame a sí mismo y, de hecho, daría como resultado una recursividad infinita si se permitiera.</span><span class="sxs-lookup"><span data-stu-id="60a63-108">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>

 <span data-ttu-id="60a63-109">**Identificador de error:** BC30298</span><span class="sxs-lookup"><span data-stu-id="60a63-109">**Error ID:** BC30298</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="60a63-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="60a63-110">To correct this error</span></span>

1. <span data-ttu-id="60a63-111">Compruebe la lista de parámetros del constructor al que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="60a63-111">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="60a63-112">Debe ser diferente del constructor que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="60a63-112">It should be different from that of the constructor making the call.</span></span>

2. <span data-ttu-id="60a63-113">Si no desea llamar a un constructor diferente, quite la llamada por `Sub New` completo.</span><span class="sxs-lookup"><span data-stu-id="60a63-113">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>

## <a name="see-also"></a><span data-ttu-id="60a63-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60a63-114">See also</span></span>

- [<span data-ttu-id="60a63-115">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="60a63-115">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
