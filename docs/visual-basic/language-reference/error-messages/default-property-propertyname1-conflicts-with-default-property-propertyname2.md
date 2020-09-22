---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b857a9ae7875a156179602cbe77558333d07b7b9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874506"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="19e06-102">La propiedad predeterminada '\<propertyname1>' está en conflicto con la propiedad predeterminada '\<propertyname2>' en la base '\<classname>' y, por tanto, se debe declarar como 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="19e06-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="19e06-103">Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="19e06-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="19e06-104">En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.</span><span class="sxs-lookup"><span data-stu-id="19e06-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="19e06-105">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="19e06-105">This message is a warning.</span></span> <span data-ttu-id="19e06-106">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="19e06-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="19e06-107">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="19e06-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="19e06-108">**Identificador de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="19e06-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="19e06-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="19e06-109">To correct this error</span></span>  
  
- <span data-ttu-id="19e06-110">Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="19e06-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e06-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19e06-111">See also</span></span>

- [<span data-ttu-id="19e06-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="19e06-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="19e06-113">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19e06-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
