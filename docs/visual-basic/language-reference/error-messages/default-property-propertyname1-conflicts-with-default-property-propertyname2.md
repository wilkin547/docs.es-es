---
title: "Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt;&#39; está en conflicto con la propiedad predeterminada &#39;&lt; propertyName2&gt;&#39; en &#39;&lt; ClassName&gt;&#39; por lo que se debe declarar como &#39; Las sombras &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords: BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="173e4-102">Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt;&#39; está en conflicto con la propiedad predeterminada &#39;&lt; propertyName2&gt;&#39; en &#39;&lt; ClassName&gt;&#39; por lo que se debe declarar como &#39; Las sombras &#39;</span><span class="sxs-lookup"><span data-stu-id="173e4-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="173e4-103">Se declara una propiedad con el mismo nombre que una propiedad definida en la clase base.</span><span class="sxs-lookup"><span data-stu-id="173e4-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="173e4-104">En esta situación, la propiedad de esta clase debe ocultar la propiedad de clase base.</span><span class="sxs-lookup"><span data-stu-id="173e4-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="173e4-105">Este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="173e4-105">This message is a warning.</span></span> <span data-ttu-id="173e4-106">De forma predeterminada, se da por supuesto que es`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="173e4-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="173e4-107">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="173e4-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="173e4-108">**Id. de error:** BC40007</span><span class="sxs-lookup"><span data-stu-id="173e4-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="173e4-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="173e4-109">To correct this error</span></span>  
  
-   <span data-ttu-id="173e4-110">Agregar el `Shadows` palabra clave para la declaración o cambie el nombre de la propiedad que se declara.</span><span class="sxs-lookup"><span data-stu-id="173e4-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173e4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="173e4-111">See Also</span></span>  
 [<span data-ttu-id="173e4-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="173e4-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="173e4-113">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="173e4-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
