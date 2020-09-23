---
title: Promoción de tipos
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 6c28ca22e96616ff09e147400bfdb2adb922ff0e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085807"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="63eff-102">Promoción de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63eff-102">Type Promotion (Visual Basic)</span></span>

<span data-ttu-id="63eff-103">Cuando se declara un elemento de programación en un módulo, Visual Basic promociona su ámbito al espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="63eff-104">Esto se conoce como *promoción de tipos*.</span><span class="sxs-lookup"><span data-stu-id="63eff-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="63eff-105">En el ejemplo siguiente se muestra una definición de esqueleto de un módulo y dos miembros de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="63eff-106">Dentro de `projModule` , los elementos de programación declarados en el nivel de módulo se promueven a `projNamespace` .</span><span class="sxs-lookup"><span data-stu-id="63eff-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="63eff-107">En el ejemplo anterior, `basicEnum` `innerClass` se promocionan y, pero `numberSub` no es, porque no se ha declarado en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="63eff-108">Efecto de la promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="63eff-108">Effect of Type Promotion</span></span>  

 <span data-ttu-id="63eff-109">El efecto de la promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="63eff-110">En el ejemplo siguiente se realizan dos llamadas al procedimiento en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="63eff-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 <span data-ttu-id="63eff-111">En el ejemplo anterior, la primera llamada utiliza cadenas de calificación completas.</span><span class="sxs-lookup"><span data-stu-id="63eff-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="63eff-112">Sin embargo, esto no es necesario debido a la promoción de tipos.</span><span class="sxs-lookup"><span data-stu-id="63eff-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="63eff-113">La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.</span><span class="sxs-lookup"><span data-stu-id="63eff-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="63eff-114">Derrota de promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="63eff-114">Defeat of Type Promotion</span></span>  

 <span data-ttu-id="63eff-115">Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro del módulo, la promoción de tipos es derrota para ese miembro del módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="63eff-116">En el ejemplo siguiente se muestra una definición de esqueleto de una enumeración y un módulo dentro del mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63eff-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 <span data-ttu-id="63eff-117">En el ejemplo anterior, Visual Basic no puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63eff-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="63eff-118">Para tener acceso a `abcSub` , debe usar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub` .</span><span class="sxs-lookup"><span data-stu-id="63eff-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="63eff-119">Sin embargo, `xyz` se sigue promoviendo la clase y se puede tener acceso a `xyzSub` la cadena de calificación más corta `thisNamespace.xyz.xyzSub` .</span><span class="sxs-lookup"><span data-stu-id="63eff-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="63eff-120">Derrotar la promoción de tipos para tipos parciales</span><span class="sxs-lookup"><span data-stu-id="63eff-120">Defeat of Type Promotion for Partial Types</span></span>  

 <span data-ttu-id="63eff-121">Si una clase o estructura dentro de un módulo utiliza la palabra clave [partial](../../../language-reference/modifiers/partial.md) , la promoción de tipos se rechaza automáticamente para esa clase o estructura, tanto si el espacio de nombres tiene un miembro con el mismo nombre como si no.</span><span class="sxs-lookup"><span data-stu-id="63eff-121">If a class or structure inside a module uses the [Partial](../../../language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="63eff-122">Otros elementos del módulo siguen siendo válidos para la promoción de tipos.</span><span class="sxs-lookup"><span data-stu-id="63eff-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="63eff-123">**Derivada.**</span><span class="sxs-lookup"><span data-stu-id="63eff-123">**Consequences.**</span></span> <span data-ttu-id="63eff-124">La anulación de la promoción de tipos de una definición parcial puede producir resultados inesperados e incluso errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="63eff-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="63eff-125">En el ejemplo siguiente se muestran definiciones parciales de esqueleto de una clase, una de las cuales está dentro de un módulo.</span><span class="sxs-lookup"><span data-stu-id="63eff-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 <span data-ttu-id="63eff-126">En el ejemplo anterior, el desarrollador podría esperar que el compilador combine las dos definiciones parciales de `sampleClass` .</span><span class="sxs-lookup"><span data-stu-id="63eff-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="63eff-127">Sin embargo, el compilador no considera la promoción de la definición parcial dentro de `sampleModule` .</span><span class="sxs-lookup"><span data-stu-id="63eff-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="63eff-128">Como resultado, intenta compilar dos clases independientes y distintas, con el mismo nombre `sampleClass` pero con diferentes rutas de acceso de calificación.</span><span class="sxs-lookup"><span data-stu-id="63eff-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="63eff-129">El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.</span><span class="sxs-lookup"><span data-stu-id="63eff-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="63eff-130">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="63eff-130">Recommendations</span></span>  

 <span data-ttu-id="63eff-131">Las siguientes recomendaciones representan una buena práctica de programación.</span><span class="sxs-lookup"><span data-stu-id="63eff-131">The following recommendations represent good programming practice.</span></span>  
  
- <span data-ttu-id="63eff-132">**Nombres únicos.**</span><span class="sxs-lookup"><span data-stu-id="63eff-132">**Unique Names.**</span></span> <span data-ttu-id="63eff-133">Cuando tenga control total sobre la nomenclatura de los elementos de programación, siempre es una buena idea usar nombres únicos en todas partes.</span><span class="sxs-lookup"><span data-stu-id="63eff-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="63eff-134">Los nombres idénticos requieren una calificación adicional y pueden dificultar la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="63eff-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="63eff-135">También pueden provocar errores sutiles y resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="63eff-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
- <span data-ttu-id="63eff-136">**Calificación completa.**</span><span class="sxs-lookup"><span data-stu-id="63eff-136">**Full Qualification.**</span></span> <span data-ttu-id="63eff-137">Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es usar siempre la calificación completa de todos los elementos de programación.</span><span class="sxs-lookup"><span data-stu-id="63eff-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="63eff-138">Si la promoción de tipos es derrota para un miembro del módulo y no se certifica totalmente ese miembro, se podría tener acceso accidentalmente a un elemento de programación diferente.</span><span class="sxs-lookup"><span data-stu-id="63eff-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63eff-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="63eff-139">See also</span></span>

- [<span data-ttu-id="63eff-140">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="63eff-140">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="63eff-141">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="63eff-141">Namespace Statement</span></span>](../../../language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="63eff-142">Partial</span><span class="sxs-lookup"><span data-stu-id="63eff-142">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="63eff-143">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63eff-143">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="63eff-144">Procedimiento para controlar el ámbito de una variable</span><span class="sxs-lookup"><span data-stu-id="63eff-144">How to: Control the Scope of a Variable</span></span>](how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="63eff-145">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="63eff-145">References to Declared Elements</span></span>](references-to-declared-elements.md)
