---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 5f279ed0a33840bb1f2321c17a1ffba412837c07
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234762"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="28fca-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28fca-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="28fca-103">Un modificador de acceso de miembro que se especifica que uno o varios elementos de programación declaran son accesibles únicamente desde dentro de su propia clase o desde una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="28fca-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28fca-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28fca-104">Remarks</span></span>  
 <span data-ttu-id="28fca-105">A veces un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento.</span><span class="sxs-lookup"><span data-stu-id="28fca-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="28fca-106">Sin embargo, si se puede heredar la clase y se espera que una jerarquía de clases derivadas, podría ser necesario para estas clases derivadas tener acceso a los datos o código.</span><span class="sxs-lookup"><span data-stu-id="28fca-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="28fca-107">En este caso, desea que el elemento que se va a estar accesible desde la clase base y de todas las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="28fca-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="28fca-108">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected`.</span><span class="sxs-lookup"><span data-stu-id="28fca-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="28fca-109">El `Protected` modificador de acceso se puede combinar con otros dos modificadores:</span><span class="sxs-lookup"><span data-stu-id="28fca-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="28fca-110">El [Protected Friend](protected-friend.md) modificador hace accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase un miembro de clase.</span><span class="sxs-lookup"><span data-stu-id="28fca-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="28fca-111">El [privada protegida](private-protected.md) modificador hace que un miembro de clase sea accesible por tipos derivados, pero sólo dentro de su ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="28fca-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="28fca-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="28fca-112">Rules</span></span>  
  
-   <span data-ttu-id="28fca-113">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="28fca-113">**Declaration Context.**</span></span> <span data-ttu-id="28fca-114">Puede usar `Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="28fca-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="28fca-115">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="28fca-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="28fca-116">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="28fca-116">Behavior</span></span>  
  
-   <span data-ttu-id="28fca-117">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="28fca-117">**Access Level.**</span></span> <span data-ttu-id="28fca-118">Todo el código en una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="28fca-118">All code in a class can access its elements.</span></span> <span data-ttu-id="28fca-119">Código de cualquier clase que deriva de una clase base puede tener acceso a toda la `Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="28fca-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="28fca-120">Esto es cierto para todas las generaciones de derivación.</span><span class="sxs-lookup"><span data-stu-id="28fca-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="28fca-121">Esto significa que puede tener acceso una clase `Protected` elementos de la clase base de la clase base y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="28fca-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="28fca-122">Acceso protegido no es un supraconjunto ni un subconjunto de acceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="28fca-122">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="28fca-123">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="28fca-123">**Access Modifiers.**</span></span> <span data-ttu-id="28fca-124">Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="28fca-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="28fca-125">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="28fca-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="28fca-126">El modificador `Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="28fca-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="28fca-127">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="28fca-128">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="28fca-129">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="28fca-130">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="28fca-131">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="28fca-132">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="28fca-133">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="28fca-134">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="28fca-135">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="28fca-136">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="28fca-137">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="28fca-138">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28fca-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="28fca-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="28fca-139">See Also</span></span>  
 [<span data-ttu-id="28fca-140">Public</span><span class="sxs-lookup"><span data-stu-id="28fca-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="28fca-141">Friend</span><span class="sxs-lookup"><span data-stu-id="28fca-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="28fca-142">Private</span><span class="sxs-lookup"><span data-stu-id="28fca-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="28fca-143">[Privado protegido](private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="28fca-143">[Private Protected](private-protected.md) </span></span>  
 <span data-ttu-id="28fca-144">[Protected Friend](protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="28fca-144">[Protected Friend](protected-friend.md) </span></span>  
 [<span data-ttu-id="28fca-145">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28fca-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="28fca-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="28fca-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="28fca-147">Estructuras</span><span class="sxs-lookup"><span data-stu-id="28fca-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="28fca-148">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="28fca-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
