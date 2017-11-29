---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="8e3cf-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="8e3cf-103">Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro de su propia clase o desde una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e3cf-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e3cf-104">Remarks</span></span>  
 <span data-ttu-id="8e3cf-105">A veces un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="8e3cf-106">Sin embargo, si se puede heredar la clase y se espera que una jerarquía de clases derivadas, podría ser necesario para estas clases derivadas tener acceso a los datos o código.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="8e3cf-107">En este caso, desea que el elemento que se va a estar accesible desde la clase base y de todas las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="8e3cf-108">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected`.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8e3cf-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="8e3cf-109">Rules</span></span>  
  
-   <span data-ttu-id="8e3cf-110">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-110">**Declaration Context.**</span></span> <span data-ttu-id="8e3cf-111">Puede usar `Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="8e3cf-112">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="8e3cf-113">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-113">**Combined Modifiers.**</span></span> <span data-ttu-id="8e3cf-114">Puede usar el `Protected` modificador junto con el [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modificador en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="8e3cf-115">Esta combinación hace que los elementos declarados accesible desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="8e3cf-116">Puede especificar `Protected Friend` solo en los miembros de clases.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8e3cf-117">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="8e3cf-117">Behavior</span></span>  
  
-   <span data-ttu-id="8e3cf-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-118">**Access Level.**</span></span> <span data-ttu-id="8e3cf-119">Todo el código en una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-119">All code in a class can access its elements.</span></span> <span data-ttu-id="8e3cf-120">Código de cualquier clase que deriva de una clase base puede tener acceso a toda la `Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="8e3cf-121">Esto es cierto para todas las generaciones de derivación.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="8e3cf-122">Esto significa que puede tener acceso una clase `Protected` elementos de la clase base de la clase base y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="8e3cf-123">Acceso protegido no es un supraconjunto ni un subconjunto de acceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="8e3cf-124">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-124">**Access Modifiers.**</span></span> <span data-ttu-id="8e3cf-125">Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="8e3cf-126">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8e3cf-127">El modificador `Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e3cf-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8e3cf-128">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="8e3cf-129">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="8e3cf-130">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="8e3cf-131">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="8e3cf-132">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="8e3cf-133">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="8e3cf-134">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="8e3cf-135">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="8e3cf-136">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="8e3cf-137">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="8e3cf-138">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="8e3cf-139">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e3cf-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e3cf-140">See Also</span></span>  
 [<span data-ttu-id="8e3cf-141">Public</span><span class="sxs-lookup"><span data-stu-id="8e3cf-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="8e3cf-142">Friend</span><span class="sxs-lookup"><span data-stu-id="8e3cf-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="8e3cf-143">Private</span><span class="sxs-lookup"><span data-stu-id="8e3cf-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="8e3cf-144">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e3cf-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="8e3cf-145">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8e3cf-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="8e3cf-146">Estructuras</span><span class="sxs-lookup"><span data-stu-id="8e3cf-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="8e3cf-147">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="8e3cf-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
