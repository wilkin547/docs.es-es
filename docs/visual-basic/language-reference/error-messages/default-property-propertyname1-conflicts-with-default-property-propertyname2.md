---
description: "Más información sobre: BC40007: la propiedad predeterminada ' <propertyname1> ' entra en conflicto con la propiedad predeterminada ' <propertyname2> ' en ' <classname> ' y, por tanto, se debe declarar como ' Shadows '"
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 8ec7e36da18bbf8dda35e1a521d64268d14b7b26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796644"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="09abb-103">BC40007: la propiedad predeterminada ' \<propertyname1> ' entra en conflicto con la propiedad predeterminada ' \<propertyname2> ' en ' \<classname> ' y, por tanto, se debe declarar como ' Shadows '</span><span class="sxs-lookup"><span data-stu-id="09abb-103">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="09abb-104">Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="09abb-104">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="09abb-105">En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.</span><span class="sxs-lookup"><span data-stu-id="09abb-105">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="09abb-106">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="09abb-106">This message is a warning.</span></span> <span data-ttu-id="09abb-107">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="09abb-107">`Shadows` is assumed by default.</span></span> <span data-ttu-id="09abb-108">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="09abb-108">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="09abb-109">**Identificador de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="09abb-109">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="09abb-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="09abb-110">To correct this error</span></span>

- <span data-ttu-id="09abb-111">Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="09abb-111">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="09abb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="09abb-112">See also</span></span>

- [<span data-ttu-id="09abb-113">Shadows</span><span class="sxs-lookup"><span data-stu-id="09abb-113">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="09abb-114">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09abb-114">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
