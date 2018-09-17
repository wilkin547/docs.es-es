---
title: Modificadores de acceso (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: ff313df9683dbc76bab684ff484b746ad05e065a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45653023"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="63ba2-102">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="63ba2-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="63ba2-103">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="63ba2-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="63ba2-104">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="63ba2-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="63ba2-105">Pueden especificarse los siguientes seis niveles de accesibilidad con los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="63ba2-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="63ba2-106">[`public`](public.md): el acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="63ba2-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="63ba2-107">[`protected`](protected.md): el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="63ba2-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="63ba2-108">[`internal`](internal.md): el acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="63ba2-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="63ba2-109">[`protected internal`](protected-internal.md): el acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="63ba2-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="63ba2-110">[`private`](private.md): el acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="63ba2-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="63ba2-111">[`private protected`](private-protected.md): el acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="63ba2-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="63ba2-112">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63ba2-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="63ba2-113">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md): usar los cuatro modificadores de acceso para declarar seis niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="63ba2-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="63ba2-114">[Dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="63ba2-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="63ba2-115">[Restricciones en el uso de niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="63ba2-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ba2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ba2-116">See Also</span></span>  
- [<span data-ttu-id="63ba2-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="63ba2-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="63ba2-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="63ba2-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="63ba2-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="63ba2-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="63ba2-120">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="63ba2-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="63ba2-121">Palabras clave de acceso</span><span class="sxs-lookup"><span data-stu-id="63ba2-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
- [<span data-ttu-id="63ba2-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="63ba2-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
