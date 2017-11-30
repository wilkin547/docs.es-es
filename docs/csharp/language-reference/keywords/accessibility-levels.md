---
title: Niveles de accesibilidad (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="53843-102">Niveles de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="53843-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="53843-103">Use los modificadores de acceso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) para especificar uno de los siguientes niveles de accesibilidad declarada para miembros.</span><span class="sxs-lookup"><span data-stu-id="53843-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="53843-104">Accesibilidad declarada</span><span class="sxs-lookup"><span data-stu-id="53843-104">Declared accessibility</span></span>|<span data-ttu-id="53843-105">Significado</span><span class="sxs-lookup"><span data-stu-id="53843-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="53843-106">El acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="53843-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="53843-107">El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="53843-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="53843-108">El acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="53843-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="53843-109">El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="53843-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="53843-110">El acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="53843-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="53843-111">Acceso está limitado a la clase contenedora o tipos derivados de la clase contenedora dentro del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="53843-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="53843-112">Solo un modificador de acceso se permite para un miembro o tipo, excepto cuando se usa el `protected internal` o `private protected` combinaciones.</span><span class="sxs-lookup"><span data-stu-id="53843-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="53843-113">No se permiten modificadores de acceso en espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="53843-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="53843-114">Los espacios de nombres no tienen restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="53843-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="53843-115">En función del contexto en el que se produce una declaración de miembro, solo se permiten ciertas accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="53843-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="53843-116">Si no se especifica ningún modificador de acceso en una declaración de miembro, se usa una accesibilidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="53843-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="53843-117">Los tipos de nivel superior, que no están anidados en otros tipos, solo pueden tener una accesibilidad `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="53843-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="53843-118">La accesibilidad predeterminada para estos tipos es `internal`.</span><span class="sxs-lookup"><span data-stu-id="53843-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="53843-119">Los tipos anidados, que son miembros de otros tipos, pueden tener accesibilidades declaradas como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="53843-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="53843-120">Miembros de</span><span class="sxs-lookup"><span data-stu-id="53843-120">Members of</span></span>|<span data-ttu-id="53843-121">Accesibilidad de miembro predeterminada</span><span class="sxs-lookup"><span data-stu-id="53843-121">Default member accessibility</span></span>|<span data-ttu-id="53843-122">Accesibilidad declarada permitida del miembro</span><span class="sxs-lookup"><span data-stu-id="53843-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="53843-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="53843-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="53843-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="53843-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="53843-125">La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="53843-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="53843-126">Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="53843-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="53843-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="53843-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53843-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="53843-128">See Also</span></span>  
 [<span data-ttu-id="53843-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="53843-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="53843-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="53843-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53843-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="53843-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="53843-132">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="53843-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="53843-133">Dominio de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="53843-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="53843-134">Restricciones en el uso de los niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="53843-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="53843-135">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="53843-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="53843-136">public</span><span class="sxs-lookup"><span data-stu-id="53843-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="53843-137">private</span><span class="sxs-lookup"><span data-stu-id="53843-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="53843-138">protected</span><span class="sxs-lookup"><span data-stu-id="53843-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="53843-139">internal</span><span class="sxs-lookup"><span data-stu-id="53843-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
