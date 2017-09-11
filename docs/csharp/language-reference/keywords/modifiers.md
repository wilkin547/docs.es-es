---
title: Modificadores (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- keywords [C#], modifiers
- modifiers [C#]
ms.assetid: c96691dd-b357-49ec-b5ae-03ca214fadfb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e2e7e5e3907ac9bb66676e749ddd55a8ac4836c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="modifiers-c-reference"></a><span data-ttu-id="7314e-102">Modificadores (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7314e-102">Modifiers (C# Reference)</span></span>
<span data-ttu-id="7314e-103">Los modificadores se usan para modificar las declaraciones de tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="7314e-103">Modifiers are used to modify declarations of types and type members.</span></span> <span data-ttu-id="7314e-104">En esta sección se presentan los modificadores de C#.</span><span class="sxs-lookup"><span data-stu-id="7314e-104">This section introduces the C# modifiers.</span></span>  
  
|<span data-ttu-id="7314e-105">Modificador</span><span class="sxs-lookup"><span data-stu-id="7314e-105">Modifier</span></span>|<span data-ttu-id="7314e-106">Propósito</span><span class="sxs-lookup"><span data-stu-id="7314e-106">Purpose</span></span>|  
|--------------|-------------|  
|[<span data-ttu-id="7314e-107">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="7314e-107">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)<br /><br /> <span data-ttu-id="7314e-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span><span class="sxs-lookup"><span data-stu-id="7314e-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span></span><br /><span data-ttu-id="7314e-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span><span class="sxs-lookup"><span data-stu-id="7314e-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span></span><br /><span data-ttu-id="7314e-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span><span class="sxs-lookup"><span data-stu-id="7314e-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span></span><br /><span data-ttu-id="7314e-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span><span class="sxs-lookup"><span data-stu-id="7314e-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span></span>|<span data-ttu-id="7314e-112">Especifica la accesibilidad declarada de tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="7314e-112">Specifies the declared accessibility of types and type members.</span></span>|  
|[<span data-ttu-id="7314e-113">abstract</span><span class="sxs-lookup"><span data-stu-id="7314e-113">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="7314e-114">Indica que una clase está diseñada solo para ser una clase base de otras clases.</span><span class="sxs-lookup"><span data-stu-id="7314e-114">Indicates that a class is intended only to be a base class of other classes.</span></span>|  
|[<span data-ttu-id="7314e-115">async</span><span class="sxs-lookup"><span data-stu-id="7314e-115">async</span></span>](../../../csharp/language-reference/keywords/async.md)|<span data-ttu-id="7314e-116">Indica que el método modificado, una expresión lambda o un método anónimo es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="7314e-116">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="7314e-117">const</span><span class="sxs-lookup"><span data-stu-id="7314e-117">const</span></span>](../../../csharp/language-reference/keywords/const.md)|<span data-ttu-id="7314e-118">Especifica que el valor del campo o la variable local no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="7314e-118">Specifies that the value of the field or the local variable cannot be modified.</span></span>|  
|[<span data-ttu-id="7314e-119">event</span><span class="sxs-lookup"><span data-stu-id="7314e-119">event</span></span>](../../../csharp/language-reference/keywords/event.md)|<span data-ttu-id="7314e-120">Declara un evento.</span><span class="sxs-lookup"><span data-stu-id="7314e-120">Declares an event.</span></span>|  
|[<span data-ttu-id="7314e-121">extern</span><span class="sxs-lookup"><span data-stu-id="7314e-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)|<span data-ttu-id="7314e-122">Indica que el método se implementa externamente.</span><span class="sxs-lookup"><span data-stu-id="7314e-122">Indicates that the method is implemented externally.</span></span>|  
|[<span data-ttu-id="7314e-123">new</span><span class="sxs-lookup"><span data-stu-id="7314e-123">new</span></span>](../../../csharp/language-reference/keywords/new.md)|<span data-ttu-id="7314e-124">Oculta explícitamente un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="7314e-124">Explicitly hides a member inherited from a base class.</span></span>|  
|[<span data-ttu-id="7314e-125">override</span><span class="sxs-lookup"><span data-stu-id="7314e-125">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="7314e-126">Proporciona una nueva implementación de un miembro virtual heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="7314e-126">Provides a new implementation of a virtual member inherited from a base class.</span></span>|  
|[<span data-ttu-id="7314e-127">partial</span><span class="sxs-lookup"><span data-stu-id="7314e-127">partial</span></span>](../../../csharp/language-reference/keywords/partial-type.md)|<span data-ttu-id="7314e-128">Define clases, structs y métodos parciales a lo largo del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7314e-128">Defines partial classes, structs and methods throughout the same assembly.</span></span>|  
|[<span data-ttu-id="7314e-129">readonly</span><span class="sxs-lookup"><span data-stu-id="7314e-129">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)|<span data-ttu-id="7314e-130">Declara un campo al que solo se pueden asignar valores como parte de la declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="7314e-130">Declares a field that can only be assigned values as part of the declaration or in a constructor in the same class.</span></span>|  
|[<span data-ttu-id="7314e-131">sealed</span><span class="sxs-lookup"><span data-stu-id="7314e-131">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="7314e-132">Especifica que una clase no se puede heredar.</span><span class="sxs-lookup"><span data-stu-id="7314e-132">Specifies that a class cannot be inherited.</span></span>|  
|[<span data-ttu-id="7314e-133">static</span><span class="sxs-lookup"><span data-stu-id="7314e-133">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="7314e-134">Declara un miembro que pertenece al propio tipo en lugar de a un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="7314e-134">Declares a member that belongs to the type itself instead of to a specific object.</span></span>|  
|[<span data-ttu-id="7314e-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="7314e-135">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)|<span data-ttu-id="7314e-136">Declara un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="7314e-136">Declares an unsafe context.</span></span>|  
|[<span data-ttu-id="7314e-137">virtual</span><span class="sxs-lookup"><span data-stu-id="7314e-137">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="7314e-138">Declara un método o un descriptor de acceso cuya implementación se puede cambiar mediante un miembro de reemplazo en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="7314e-138">Declares a method or an accessor whose implementation can be changed by an overriding member in a derived class.</span></span>|  
|[<span data-ttu-id="7314e-139">volatile</span><span class="sxs-lookup"><span data-stu-id="7314e-139">volatile</span></span>](../../../csharp/language-reference/keywords/volatile.md)|<span data-ttu-id="7314e-140">Indica que un campo se puede modificar en el programa mediante un elemento como el sistema operativo, el hardware o un subproceso que se ejecute en paralelo.</span><span class="sxs-lookup"><span data-stu-id="7314e-140">Indicates that a field can be modified in the program by something such as the operating system, the hardware, or a concurrently executing thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7314e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="7314e-141">See Also</span></span>  
 <span data-ttu-id="7314e-142">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7314e-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7314e-143">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7314e-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7314e-144">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7314e-144">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

