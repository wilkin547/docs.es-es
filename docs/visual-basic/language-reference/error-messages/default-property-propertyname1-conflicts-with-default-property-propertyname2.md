---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160612"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="d546c-102">BC40007: la propiedad predeterminada ' \<propertyname1> ' entra en conflicto con la propiedad predeterminada ' \<propertyname2> ' en ' \<classname> ' y, por tanto, se debe declarar como ' Shadows '</span><span class="sxs-lookup"><span data-stu-id="d546c-102">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="d546c-103">Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="d546c-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="d546c-104">En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.</span><span class="sxs-lookup"><span data-stu-id="d546c-104">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="d546c-105">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d546c-105">This message is a warning.</span></span> <span data-ttu-id="d546c-106">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="d546c-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="d546c-107">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d546c-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="d546c-108">**Identificador de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="d546c-108">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d546c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d546c-109">To correct this error</span></span>

- <span data-ttu-id="d546c-110">Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="d546c-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="d546c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d546c-111">See also</span></span>

- [<span data-ttu-id="d546c-112">Sombras</span><span class="sxs-lookup"><span data-stu-id="d546c-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="d546c-113">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d546c-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
