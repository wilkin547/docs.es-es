---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 3e30267c8aa11ce97b3b3064ff0954378dab57af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959799"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="bccf6-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bccf6-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="bccf6-103">Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del ensamblado que contiene su declaración.</span><span class="sxs-lookup"><span data-stu-id="bccf6-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bccf6-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bccf6-104">Remarks</span></span>  
 <span data-ttu-id="bccf6-105">En muchos casos, desea que los elementos de programación, como clases y estructuras, se usen en todo el ensamblado, no solo en el componente que los declara.</span><span class="sxs-lookup"><span data-stu-id="bccf6-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="bccf6-106">Sin embargo, es posible que no desee que el código fuera del ensamblado tenga acceso a ellos (por ejemplo, si la aplicación es propietaria).</span><span class="sxs-lookup"><span data-stu-id="bccf6-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="bccf6-107">Si desea limitar el acceso a un elemento de esta manera, puede declararlo mediante el `Friend` modificador.</span><span class="sxs-lookup"><span data-stu-id="bccf6-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="bccf6-108">El código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado pueden `Friend` tener acceso a todos los elementos de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bccf6-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="bccf6-109">`Friend`el acceso es a menudo el nivel preferido para los elementos de programación de `Friend` una aplicación y es el nivel de acceso predeterminado de una interfaz, un módulo, una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="bccf6-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="bccf6-110">Solo se puede `Friend` usar en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bccf6-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="bccf6-111">Por consiguiente, el contexto de la `Friend` declaración de un elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bccf6-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="bccf6-112">También puede usar el modificador de acceso [Friend protegido](protected-friend.md) , que hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase.</span><span class="sxs-lookup"><span data-stu-id="bccf6-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="bccf6-113">Para restringir el acceso a un miembro de dentro de su clase y de las clases derivadas en el mismo ensamblado, se utiliza el modificador de acceso [protegido privado](private-protected.md) .</span><span class="sxs-lookup"><span data-stu-id="bccf6-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="bccf6-114">Para obtener una comparación `Friend` de y los demás modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bccf6-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bccf6-115">Puede especificar que otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y `Friend`miembros marcados como.</span><span class="sxs-lookup"><span data-stu-id="bccf6-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="bccf6-116">Para más información, vea [Ensamblados de confianza](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bccf6-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bccf6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bccf6-117">Example</span></span>  
 <span data-ttu-id="bccf6-118">La siguiente clase usa el `Friend` modificador para permitir que otros elementos de programación del mismo ensamblado tengan acceso a determinados miembros.</span><span class="sxs-lookup"><span data-stu-id="bccf6-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="bccf6-119">Uso</span><span class="sxs-lookup"><span data-stu-id="bccf6-119">Usage</span></span>  
 <span data-ttu-id="bccf6-120">Puede usar el `Friend` modificador en estos contextos:</span><span class="sxs-lookup"><span data-stu-id="bccf6-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="bccf6-121">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="bccf6-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="bccf6-123">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="bccf6-124">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="bccf6-125">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="bccf6-126">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="bccf6-127">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="bccf6-128">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bccf6-129">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="bccf6-130">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="bccf6-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bccf6-132">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="bccf6-133">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bccf6-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bccf6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccf6-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="bccf6-135">Public</span><span class="sxs-lookup"><span data-stu-id="bccf6-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="bccf6-136">Protected</span><span class="sxs-lookup"><span data-stu-id="bccf6-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="bccf6-137">Private</span><span class="sxs-lookup"><span data-stu-id="bccf6-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="bccf6-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="bccf6-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="bccf6-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="bccf6-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="bccf6-140">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bccf6-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="bccf6-141">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="bccf6-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bccf6-142">Estructuras</span><span class="sxs-lookup"><span data-stu-id="bccf6-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="bccf6-143">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="bccf6-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
