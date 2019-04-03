---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813176"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="ec245-102">Propiedad predeterminada '\<nombrepropiedad1 >' entra en conflicto con la propiedad predeterminada '\<nombrepropiedad2 >' en '\<classname >', por lo que se debe declarar como 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="ec245-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="ec245-103">Se declara una propiedad con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="ec245-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="ec245-104">En esta situación, la propiedad de esta clase debe ocultar la propiedad de clase base.</span><span class="sxs-lookup"><span data-stu-id="ec245-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="ec245-105">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ec245-105">This message is a warning.</span></span> <span data-ttu-id="ec245-106">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="ec245-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="ec245-107">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ec245-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ec245-108">**Identificador de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="ec245-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ec245-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ec245-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ec245-110">Agregar el `Shadows` palabra clave para la declaración o cambie el nombre de la propiedad que se declara.</span><span class="sxs-lookup"><span data-stu-id="ec245-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec245-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec245-111">See also</span></span>

- [<span data-ttu-id="ec245-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="ec245-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ec245-113">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec245-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
