---
title: Modificadores de acceso (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d63cf724a2364059e5f3327254a9ec95f7493e5e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="152ed-102">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="152ed-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="152ed-103">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="152ed-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="152ed-104">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="152ed-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="152ed-105">Pueden especificarse los siguientes seis niveles de accesibilidad con los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="152ed-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="152ed-106">[`public`](public.md): el acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="152ed-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="152ed-107">[`protected`](protected.md): el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="152ed-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="152ed-108">[`internal`](internal.md): el acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="152ed-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="152ed-109">[`protected internal`](protected-internal.md): el acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="152ed-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="152ed-110">[`private`](private.md): el acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="152ed-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="152ed-111">[`private protected`](private-protected.md): el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="152ed-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="152ed-112">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="152ed-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="152ed-113">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md): usar los cuatro modificadores de acceso para declarar seis niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="152ed-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="152ed-114">[Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="152ed-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="152ed-115">[Restricciones en el uso de niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="152ed-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152ed-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="152ed-116">See Also</span></span>  
 [<span data-ttu-id="152ed-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="152ed-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="152ed-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="152ed-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="152ed-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="152ed-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="152ed-120">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="152ed-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="152ed-121">Palabras clave de acceso</span><span class="sxs-lookup"><span data-stu-id="152ed-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="152ed-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="152ed-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
