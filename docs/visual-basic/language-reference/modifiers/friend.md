---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a><span data-ttu-id="85c37-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85c37-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="85c37-103">Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro del ensamblado que contiene su declaración.</span><span class="sxs-lookup"><span data-stu-id="85c37-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85c37-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85c37-104">Remarks</span></span>  
 <span data-ttu-id="85c37-105">En muchos casos, desea que elementos de programación como las clases y estructuras que se usará en todo el ensamblado, no solo por el componente que se declara.</span><span class="sxs-lookup"><span data-stu-id="85c37-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="85c37-106">Sin embargo, no conviene que sean accesibles para el código fuera del ensamblado (por ejemplo, si la aplicación es propietaria).</span><span class="sxs-lookup"><span data-stu-id="85c37-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="85c37-107">Si desea limitar el acceso a un elemento de esta manera, puede declarar mediante el `Friend` modificador.</span><span class="sxs-lookup"><span data-stu-id="85c37-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="85c37-108">Código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado puede tener acceso a toda la `Friend` elementos en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="85c37-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="85c37-109">`Friend`acceso a menudo es el nivel preferido para elementos de programación de la aplicación, y `Friend` es el acceso predeterminado de una interfaz, un módulo, una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="85c37-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="85c37-110">Puede usar `Friend` en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="85c37-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="85c37-111">Por lo tanto, el contexto de la declaración de un `Friend` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="85c37-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="85c37-112">Puede usar el `Friend` modificador junto con el [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modificador en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="85c37-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="85c37-113">Esta combinación de ambos confiere `Friend` acceso y acceso protegido a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="85c37-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="85c37-114">Puede especificar `Protected Friend` solo en los miembros de clases.</span><span class="sxs-lookup"><span data-stu-id="85c37-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="85c37-115">Para obtener una comparación de `Friend` y otros modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="85c37-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85c37-116">Puede especificar que el otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y miembros que están marcados como `Friend`.</span><span class="sxs-lookup"><span data-stu-id="85c37-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="85c37-117">Para más información, vea [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="85c37-117">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c37-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85c37-118">Example</span></span>  
 <span data-ttu-id="85c37-119">La siguiente clase utiliza el `Friend` modificador para permitir que otros elementos de programación dentro del mismo ensamblado para tener acceso a ciertos miembros.</span><span class="sxs-lookup"><span data-stu-id="85c37-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="85c37-120">Uso</span><span class="sxs-lookup"><span data-stu-id="85c37-120">Usage</span></span>  
 <span data-ttu-id="85c37-121">Puede usar el `Friend` modificador en estos contextos:</span><span class="sxs-lookup"><span data-stu-id="85c37-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="85c37-122">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="85c37-123">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="85c37-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="85c37-125">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="85c37-126">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="85c37-127">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="85c37-128">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="85c37-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="85c37-130">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="85c37-131">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="85c37-132">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="85c37-133">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="85c37-134">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85c37-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="85c37-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="85c37-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="85c37-136">Public</span><span class="sxs-lookup"><span data-stu-id="85c37-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="85c37-137">Protected</span><span class="sxs-lookup"><span data-stu-id="85c37-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="85c37-138">Private</span><span class="sxs-lookup"><span data-stu-id="85c37-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="85c37-139">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85c37-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="85c37-140">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="85c37-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="85c37-141">Estructuras</span><span class="sxs-lookup"><span data-stu-id="85c37-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="85c37-142">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="85c37-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
