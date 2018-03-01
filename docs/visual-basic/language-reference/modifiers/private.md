---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a><span data-ttu-id="8d73a-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d73a-102">Private (Visual Basic)</span></span>
<span data-ttu-id="8d73a-103">Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro de su contexto de declaración, incluyendo desde dentro de los tipos contenidos.</span><span class="sxs-lookup"><span data-stu-id="8d73a-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d73a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d73a-104">Remarks</span></span>  
 <span data-ttu-id="8d73a-105">Si un elemento de programación representa la funcionalidad de propietario, o contiene datos confidenciales, normalmente es conveniente limitar el acceso a él como estrictamente como sea posible.</span><span class="sxs-lookup"><span data-stu-id="8d73a-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="8d73a-106">Alcanzar la limitación máxima al permitir que el módulo, clase o estructura que define para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="8d73a-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="8d73a-107">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private`.</span><span class="sxs-lookup"><span data-stu-id="8d73a-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8d73a-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="8d73a-108">Rules</span></span>  
  
-   <span data-ttu-id="8d73a-109">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="8d73a-109">**Declaration Context.**</span></span> <span data-ttu-id="8d73a-110">Solo se puede usar `Private` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="8d73a-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="8d73a-111">Esto significa que el contexto de la declaración de un `Private` elemento debe ser un módulo, clase o estructura y no puede ser un archivo de código fuente, el espacio de nombres, la interfaz o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8d73a-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8d73a-112">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="8d73a-112">Behavior</span></span>  
  
-   <span data-ttu-id="8d73a-113">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="8d73a-113">**Access Level.**</span></span> <span data-ttu-id="8d73a-114">Puede tener acceso todo el código dentro de un contexto de declaración su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="8d73a-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="8d73a-115">Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="8d73a-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="8d73a-116">Ningún código fuera del contexto de declaración puede tener acceso a su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="8d73a-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="8d73a-117">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="8d73a-117">**Access Modifiers.**</span></span> <span data-ttu-id="8d73a-118">Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="8d73a-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="8d73a-119">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8d73a-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8d73a-120">El modificador `Private` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d73a-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8d73a-121">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="8d73a-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="8d73a-123">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="8d73a-124">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="8d73a-125">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="8d73a-126">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="8d73a-127">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="8d73a-128">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="8d73a-129">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="8d73a-130">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="8d73a-131">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="8d73a-132">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8d73a-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d73a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d73a-133">See Also</span></span>  
 [<span data-ttu-id="8d73a-134">Public</span><span class="sxs-lookup"><span data-stu-id="8d73a-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="8d73a-135">Protected</span><span class="sxs-lookup"><span data-stu-id="8d73a-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="8d73a-136">Friend</span><span class="sxs-lookup"><span data-stu-id="8d73a-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="8d73a-137">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d73a-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="8d73a-138">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8d73a-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="8d73a-139">Estructuras</span><span class="sxs-lookup"><span data-stu-id="8d73a-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="8d73a-140">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="8d73a-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
