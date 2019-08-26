---
title: 'Modificadores de acceso: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 5568d79c4a13b7b0db5a46bb4ebb2168ea66a2c9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606093"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="7a6e0-102">Modificadores de acceso (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7a6e0-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="7a6e0-103">Los modificadores de acceso son palabras clave que se usan para especificar la accesibilidad declarada de un miembro o un tipo.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="7a6e0-104">En esta sección se presentan los cuatro modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="7a6e0-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="7a6e0-105">Pueden especificarse los siguientes seis niveles de accesibilidad con los modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="7a6e0-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="7a6e0-106">[`public`](public.md): El acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="7a6e0-107">[`protected`](protected.md): El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="7a6e0-108">[`internal`](internal.md): El acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="7a6e0-109">[`protected internal`](protected-internal.md): El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="7a6e0-110">[`private`](private.md): El acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="7a6e0-111">[`private protected`](private-protected.md): El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="7a6e0-112">En esta sección también se presenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a6e0-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="7a6e0-113">[Niveles de accesibilidad](./accessibility-levels.md): Usar los cuatro modificadores de acceso para declarar seis niveles de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-113">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="7a6e0-114">[Dominio de accesibilidad](./accessibility-domain.md): especifica en qué secciones del programa se puede hacer referencia a dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-114">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="7a6e0-115">[Restricciones en el uso de los niveles de accesibilidad](./restrictions-on-using-accessibility-levels.md): un resumen de las restricciones sobre usar niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="7a6e0-115">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6e0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a6e0-116">See also</span></span>

- [<span data-ttu-id="7a6e0-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7a6e0-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7a6e0-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7a6e0-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7a6e0-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7a6e0-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="7a6e0-120">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="7a6e0-120">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="7a6e0-121">Palabras clave de acceso</span><span class="sxs-lookup"><span data-stu-id="7a6e0-121">Access Keywords</span></span>](./access-keywords.md)
- [<span data-ttu-id="7a6e0-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="7a6e0-122">Modifiers</span></span>](./modifiers.md)
