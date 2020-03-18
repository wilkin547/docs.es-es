---
title: 'Niveles de accesibilidad: Referencia de C#'
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713814"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="47b48-102">Niveles de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="47b48-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="47b48-103">Use los modificadores de acceso `public`, `protected`, `internal` o `private` para especificar uno de los siguientes niveles de accesibilidad declarada para miembros.</span><span class="sxs-lookup"><span data-stu-id="47b48-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="47b48-104">Accesibilidad declarada</span><span class="sxs-lookup"><span data-stu-id="47b48-104">Declared accessibility</span></span>|<span data-ttu-id="47b48-105">Significado</span><span class="sxs-lookup"><span data-stu-id="47b48-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="47b48-106">El acceso no está restringido.</span><span class="sxs-lookup"><span data-stu-id="47b48-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="47b48-107">El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="47b48-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="47b48-108">El acceso está limitado al ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="47b48-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="47b48-109">El acceso está limitado al ensamblado actual o a los tipos derivados de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="47b48-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="47b48-110">El acceso está limitado al tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="47b48-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="47b48-111">El acceso está limitado a la clase contenedora o a los tipos derivados de la clase contenedora que hay en el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="47b48-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="47b48-112">Disponible desde la versión C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="47b48-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="47b48-113">Solo se permite un modificador de acceso para un miembro o tipo, excepto cuando se usan las combinaciones `protected internal` o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="47b48-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="47b48-114">No se permiten modificadores de acceso en espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="47b48-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="47b48-115">Los espacios de nombres no tienen restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="47b48-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="47b48-116">En función del contexto en el que se produce una declaración de miembro, solo se permiten ciertas accesibilidades declaradas.</span><span class="sxs-lookup"><span data-stu-id="47b48-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="47b48-117">Si no se especifica ningún modificador de acceso en una declaración de miembro, se usa una accesibilidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47b48-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="47b48-118">Los tipos de nivel superior, que no están anidados en otros tipos, solo pueden tener una accesibilidad `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="47b48-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="47b48-119">La accesibilidad predeterminada para estos tipos es `internal`.</span><span class="sxs-lookup"><span data-stu-id="47b48-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="47b48-120">Los tipos anidados, que son miembros de otros tipos, pueden tener accesibilidades declaradas como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47b48-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="47b48-121">Miembros de</span><span class="sxs-lookup"><span data-stu-id="47b48-121">Members of</span></span>|<span data-ttu-id="47b48-122">Accesibilidad de miembro predeterminada</span><span class="sxs-lookup"><span data-stu-id="47b48-122">Default member accessibility</span></span>|<span data-ttu-id="47b48-123">Accesibilidad declarada permitida del miembro</span><span class="sxs-lookup"><span data-stu-id="47b48-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="47b48-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="47b48-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="47b48-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="47b48-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="47b48-126">La accesibilidad de un tipo anidado depende de su [dominio de accesibilidad](./accessibility-domain.md), que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato.</span><span class="sxs-lookup"><span data-stu-id="47b48-126">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="47b48-127">Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="47b48-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="47b48-128">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="47b48-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47b48-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="47b48-129">See also</span></span>

- [<span data-ttu-id="47b48-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="47b48-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47b48-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="47b48-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="47b48-132">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="47b48-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="47b48-133">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="47b48-133">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="47b48-134">Dominio de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="47b48-134">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="47b48-135">Restricciones en el uso de los niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="47b48-135">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="47b48-136">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="47b48-136">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="47b48-137">public</span><span class="sxs-lookup"><span data-stu-id="47b48-137">public</span></span>](./public.md)
- [<span data-ttu-id="47b48-138">private</span><span class="sxs-lookup"><span data-stu-id="47b48-138">private</span></span>](./private.md)
- [<span data-ttu-id="47b48-139">protected</span><span class="sxs-lookup"><span data-stu-id="47b48-139">protected</span></span>](./protected.md)
- [<span data-ttu-id="47b48-140">internal</span><span class="sxs-lookup"><span data-stu-id="47b48-140">internal</span></span>](./internal.md)
