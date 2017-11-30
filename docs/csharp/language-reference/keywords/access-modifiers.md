---
title: Modificadores de acceso (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="71356-102">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="71356-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="71356-103">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="71356-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="71356-104">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="71356-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="71356-105">public</span><span class="sxs-lookup"><span data-stu-id="71356-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="71356-106">protected</span><span class="sxs-lookup"><span data-stu-id="71356-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="71356-107">internal</span><span class="sxs-lookup"><span data-stu-id="71356-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="71356-108">private</span><span class="sxs-lookup"><span data-stu-id="71356-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="71356-109">Los siguientes seis niveles de accesibilidad pueden especificarse mediante los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="71356-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="71356-110">`public`: el acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="71356-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="71356-111">`protected`: el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="71356-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="71356-112">`internal`: el acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="71356-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="71356-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Acceso está limitado al ensamblado actual o tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="71356-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="71356-114">`private`: el acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="71356-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="71356-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Acceso está limitado a la clase contenedora o tipos derivados de la clase contenedora dentro del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="71356-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="71356-116">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="71356-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="71356-117">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md): mediante los modificadores de cuatro acceso para declarar los seis niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="71356-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="71356-118">[Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="71356-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="71356-119">[Restricciones en el uso de niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="71356-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71356-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="71356-120">See Also</span></span>  
 [<span data-ttu-id="71356-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="71356-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="71356-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="71356-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="71356-123">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="71356-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="71356-124">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="71356-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="71356-125">Palabras clave de acceso</span><span class="sxs-lookup"><span data-stu-id="71356-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="71356-126">Modificadores</span><span class="sxs-lookup"><span data-stu-id="71356-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
