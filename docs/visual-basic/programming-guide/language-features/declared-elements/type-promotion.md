---
title: "Promoción de tipos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="f8e92-102">Promoción de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8e92-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="f8e92-103">Cuando se declara un elemento de programación en un módulo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promueve su ámbito al espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="f8e92-104">Esto se conoce como *promoción de tipo*.</span><span class="sxs-lookup"><span data-stu-id="f8e92-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="f8e92-105">En el ejemplo siguiente se muestra un esquema de definición de un módulo y dos miembros de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="f8e92-106">Dentro de `projModule`, programación elementos declarados en el nivel de módulo se promueven a `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="f8e92-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="f8e92-107">En el ejemplo anterior, `basicEnum` y `innerClass` se promocionan, pero `numberSub` no, es porque no se ha declarado en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="f8e92-108">Efecto de promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="f8e92-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="f8e92-109">El efecto de la promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="f8e92-110">En el ejemplo siguiente se realiza dos llamadas al procedimiento en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f8e92-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="f8e92-111">En el ejemplo anterior, la primera llamada usa cadenas de calificación completas.</span><span class="sxs-lookup"><span data-stu-id="f8e92-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="f8e92-112">Sin embargo, esto no es necesario debido a la promoción de tipos.</span><span class="sxs-lookup"><span data-stu-id="f8e92-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="f8e92-113">La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.</span><span class="sxs-lookup"><span data-stu-id="f8e92-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="f8e92-114">Rechazo de promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="f8e92-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="f8e92-115">Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro del módulo, la promoción de tipos se rechaza para ese miembro del módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="f8e92-116">En el ejemplo siguiente se muestra un esquema de definición de una enumeración y un módulo dentro del mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f8e92-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="f8e92-117">En el ejemplo anterior, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no se puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f8e92-117">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="f8e92-118">Para tener acceso a `abcSub`, debe utilizar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="f8e92-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="f8e92-119">Sin embargo, la clase `xyz` todavía se promueve, y puede tener acceso a `xyzSub` con la cadena de calificación más corta `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="f8e92-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="f8e92-120">Rechazo de promoción de tipos para tipos parciales.</span><span class="sxs-lookup"><span data-stu-id="f8e92-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="f8e92-121">Si una clase o estructura dentro de un módulo usa la [parcial](../../../../visual-basic/language-reference/modifiers/partial.md) palabra clave, se rechaza automáticamente para esa clase o estructura, la promoción de tipos si el espacio de nombres tiene un miembro con el mismo nombre o no.</span><span class="sxs-lookup"><span data-stu-id="f8e92-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="f8e92-122">Otros elementos en el módulo son aún aptos para la promoción de tipos.</span><span class="sxs-lookup"><span data-stu-id="f8e92-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="f8e92-123">**Consecuencias.**</span><span class="sxs-lookup"><span data-stu-id="f8e92-123">**Consequences.**</span></span> <span data-ttu-id="f8e92-124">Rechazo de promoción de tipos de una definición parcial puede producir resultados inesperados e incluso errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="f8e92-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="f8e92-125">En el ejemplo siguiente se muestra el esqueletos definiciones parciales de una clase, una de las cuales está dentro de un módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e92-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="f8e92-126">En el ejemplo anterior, el desarrollador podría esperar que el compilador para combinar las dos definiciones parciales de `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="f8e92-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="f8e92-127">Sin embargo, el compilador no tiene en cuenta para la definición parcial dentro de la promoción `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="f8e92-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="f8e92-128">Como resultado, intenta compilar dos clases independientes y distintas, ambos denominados `sampleClass` pero con las rutas de acceso de calificación diferentes.</span><span class="sxs-lookup"><span data-stu-id="f8e92-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="f8e92-129">El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.</span><span class="sxs-lookup"><span data-stu-id="f8e92-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="f8e92-130">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f8e92-130">Recommendations</span></span>  
 <span data-ttu-id="f8e92-131">Las recomendaciones siguientes representan buena práctica de programación.</span><span class="sxs-lookup"><span data-stu-id="f8e92-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="f8e92-132">**Nombres únicos.**</span><span class="sxs-lookup"><span data-stu-id="f8e92-132">**Unique Names.**</span></span> <span data-ttu-id="f8e92-133">Si tiene control total sobre la nomenclatura de los elementos de programación, siempre es una buena idea usar nombres únicos en todas partes.</span><span class="sxs-lookup"><span data-stu-id="f8e92-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="f8e92-134">Nombres idénticos requieren calificación adicional y pueden hacer que el código sea más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="f8e92-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="f8e92-135">También puede llevar a errores imperceptibles y resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="f8e92-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="f8e92-136">**Usar el nombre completo.**</span><span class="sxs-lookup"><span data-stu-id="f8e92-136">**Full Qualification.**</span></span> <span data-ttu-id="f8e92-137">Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es utilizar siempre la calificación completa para todos los elementos de programación.</span><span class="sxs-lookup"><span data-stu-id="f8e92-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="f8e92-138">Si la promoción de tipos se rechaza para un miembro del módulo y no completos a ese miembro, sin darse cuenta podría tener acceso a un elemento de programación diferente.</span><span class="sxs-lookup"><span data-stu-id="f8e92-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e92-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8e92-139">See Also</span></span>  
 [<span data-ttu-id="f8e92-140">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f8e92-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="f8e92-141">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f8e92-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="f8e92-142">Partial</span><span class="sxs-lookup"><span data-stu-id="f8e92-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="f8e92-143">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8e92-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="f8e92-144">Controlar el ámbito de una variable</span><span class="sxs-lookup"><span data-stu-id="f8e92-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="f8e92-145">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="f8e92-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
