---
description: 'Modificadores de acceso: Referencia de C#'
title: 'Modificadores de acceso: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: e941fc673c508f10863ee49b6544d6886bd594a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168821"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="bee8b-103">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bee8b-103">Access Modifiers (C# Reference)</span></span>

<span data-ttu-id="bee8b-104">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="bee8b-104">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="bee8b-105">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="bee8b-105">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="bee8b-106">Pueden especificarse los siguientes seis niveles de accesibilidad con los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="bee8b-106">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="bee8b-107">[`public`](public.md): El acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="bee8b-107">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="bee8b-108">[`protected`](protected.md): El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="bee8b-108">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="bee8b-109">[`internal`](internal.md): El acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="bee8b-109">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="bee8b-110">[`protected internal`](protected-internal.md): El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="bee8b-110">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="bee8b-111">[`private`](private.md): El acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="bee8b-111">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="bee8b-112">[`private protected`](private-protected.md): El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="bee8b-112">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="bee8b-113">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bee8b-113">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="bee8b-114">[Niveles de accesibilidad](./accessibility-levels.md): usar los cuatro modificadores de acceso para declarar seis niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="bee8b-114">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="bee8b-115">[Dominio de accesibilidad](./accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="bee8b-115">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="bee8b-116">[Restricciones en el uso de niveles de accesibilidad](./restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="bee8b-116">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee8b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bee8b-117">See also</span></span>

- [<span data-ttu-id="bee8b-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bee8b-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bee8b-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bee8b-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bee8b-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="bee8b-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="bee8b-121">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="bee8b-121">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="bee8b-122">Palabras clave de acceso</span><span class="sxs-lookup"><span data-stu-id="bee8b-122">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="bee8b-123">Modificadores</span><span class="sxs-lookup"><span data-stu-id="bee8b-123">Modifiers</span></span>](index.md)
