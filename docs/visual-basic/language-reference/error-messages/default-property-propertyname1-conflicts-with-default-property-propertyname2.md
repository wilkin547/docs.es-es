---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 37f98ce8120d5861552819690f9d5f22c9959a0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409730"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="0f9de-102">La propiedad predeterminada '\<propertyname1>' está en conflicto con la propiedad predeterminada '\<propertyname2>' en la base '\<classname>' y, por tanto, se debe declarar como 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="0f9de-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="0f9de-103">Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="0f9de-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="0f9de-104">En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.</span><span class="sxs-lookup"><span data-stu-id="0f9de-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="0f9de-105">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="0f9de-105">This message is a warning.</span></span> <span data-ttu-id="0f9de-106">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="0f9de-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="0f9de-107">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0f9de-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0f9de-108">**Identificador de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="0f9de-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f9de-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0f9de-109">To correct this error</span></span>  
  
- <span data-ttu-id="0f9de-110">Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="0f9de-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f9de-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f9de-111">See also</span></span>

- [<span data-ttu-id="0f9de-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="0f9de-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="0f9de-113">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f9de-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
