---
title: Niveles de accesibilidad (Referencia de C#)
ms.date: 12/06/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 816ee0fab3fae21bff2ffbfcbfe39d04dcf95025
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="c7ae5-102">Niveles de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c7ae5-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="c7ae5-103">Use los modificadores de acceso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) para especificar uno de los siguientes niveles de accesibilidad declarada para miembros.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="c7ae5-104">Accesibilidad declarada</span><span class="sxs-lookup"><span data-stu-id="c7ae5-104">Declared accessibility</span></span>|<span data-ttu-id="c7ae5-105">Significado</span><span class="sxs-lookup"><span data-stu-id="c7ae5-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="c7ae5-106">El acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="c7ae5-107">El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="c7ae5-108">El acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="c7ae5-109">El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="c7ae5-110">El acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="c7ae5-111">El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="c7ae5-112">Disponible desde la versión C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="c7ae5-113">Solo se permite un modificador de acceso para un miembro o tipo, excepto cuando se usan las combinaciones `protected internal` o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="c7ae5-114">No se permiten modificadores de acceso en espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="c7ae5-115">Los espacios de nombres no tienen restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="c7ae5-116">En función del contexto en el que se produce una declaración de miembro, solo se permiten ciertas accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="c7ae5-117">Si no se especifica ningún modificador de acceso en una declaración de miembro, se usa una accesibilidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="c7ae5-118">Los tipos de nivel superior, que no están anidados en otros tipos, solo pueden tener una accesibilidad `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="c7ae5-119">La accesibilidad predeterminada para estos tipos es `internal`.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="c7ae5-120">Los tipos anidados, que son miembros de otros tipos, pueden tener accesibilidades declaradas como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="c7ae5-121">Miembros de</span><span class="sxs-lookup"><span data-stu-id="c7ae5-121">Members of</span></span>|<span data-ttu-id="c7ae5-122">Accesibilidad de miembro predeterminada</span><span class="sxs-lookup"><span data-stu-id="c7ae5-122">Default member accessibility</span></span>|<span data-ttu-id="c7ae5-123">Accesibilidad declarada permitida del miembro</span><span class="sxs-lookup"><span data-stu-id="c7ae5-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="c7ae5-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7ae5-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="c7ae5-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7ae5-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="c7ae5-126">La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="c7ae5-127">Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="c7ae5-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c7ae5-128">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c7ae5-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7ae5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7ae5-129">See Also</span></span>  
 [<span data-ttu-id="c7ae5-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c7ae5-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c7ae5-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c7ae5-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c7ae5-132">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="c7ae5-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c7ae5-133">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="c7ae5-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="c7ae5-134">Dominio de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c7ae5-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="c7ae5-135">Restricciones en el uso de los niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c7ae5-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="c7ae5-136">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="c7ae5-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="c7ae5-137">public</span><span class="sxs-lookup"><span data-stu-id="c7ae5-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="c7ae5-138">private</span><span class="sxs-lookup"><span data-stu-id="c7ae5-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="c7ae5-139">protected</span><span class="sxs-lookup"><span data-stu-id="c7ae5-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="c7ae5-140">internal</span><span class="sxs-lookup"><span data-stu-id="c7ae5-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
