---
description: 'Más información acerca de: Partial (Visual Basic)'
title: Parcial
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: bf2d8b06b83f4a90ec2f4edd52405b58695c26e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701019"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="517f6-103">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="517f6-103">Partial (Visual Basic)</span></span>

<span data-ttu-id="517f6-104">Indica que una declaración de tipo es una definición parcial del tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-104">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="517f6-105">Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="517f6-105">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="517f6-106">Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee,</span><span class="sxs-lookup"><span data-stu-id="517f6-106">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="517f6-107">pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="517f6-107">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="517f6-108">Visual Basic admite *métodos parciales*, que normalmente se implementan en clases parciales.</span><span class="sxs-lookup"><span data-stu-id="517f6-108">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="517f6-109">Para obtener más información, vea [métodos parciales](../../programming-guide/language-features/procedures/partial-methods.md) y [Sub Statement](../statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-109">For more information, see [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="517f6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="517f6-110">Syntax</span></span>  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="517f6-111">Partes</span><span class="sxs-lookup"><span data-stu-id="517f6-111">Parts</span></span>  
  
|<span data-ttu-id="517f6-112">Término</span><span class="sxs-lookup"><span data-stu-id="517f6-112">Term</span></span>|<span data-ttu-id="517f6-113">Definición</span><span class="sxs-lookup"><span data-stu-id="517f6-113">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="517f6-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-114">Optional.</span></span> <span data-ttu-id="517f6-115">Lista de atributos que se aplican a este tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-115">List of attributes that apply to this type.</span></span> <span data-ttu-id="517f6-116">Debe incluir la [lista de atributos](../statements/attribute-list.md) entre corchetes angulares ( `< >` ).</span><span class="sxs-lookup"><span data-stu-id="517f6-116">You must enclose the [Attribute List](../statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="517f6-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-117">Optional.</span></span> <span data-ttu-id="517f6-118">Especifica qué código puede tener acceso a este tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-118">Specifies what code can access this type.</span></span> <span data-ttu-id="517f6-119">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-119">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="517f6-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-120">Optional.</span></span> <span data-ttu-id="517f6-121">Vea [Shadows](shadows.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-121">See [Shadows](shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="517f6-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-122">Optional.</span></span> <span data-ttu-id="517f6-123">Vea [MustInherit](mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-123">See [MustInherit](mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="517f6-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-124">Optional.</span></span> <span data-ttu-id="517f6-125">Vea [NotInheritable](notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-125">See [NotInheritable](notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="517f6-126">Necesario.</span><span class="sxs-lookup"><span data-stu-id="517f6-126">Required.</span></span> <span data-ttu-id="517f6-127">Nombre de este tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-127">Name of this type.</span></span> <span data-ttu-id="517f6-128">Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-128">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="517f6-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-129">Optional.</span></span> <span data-ttu-id="517f6-130">Especifica que se trata de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="517f6-130">Specifies that this is a generic type.</span></span> <span data-ttu-id="517f6-131">Vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-131">See [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="517f6-132">Obligatorio si se usa [de](../statements/of-clause.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-132">Required if you use [Of](../statements/of-clause.md).</span></span> <span data-ttu-id="517f6-133">Consulte [lista de tipos](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-133">See [Type List](../statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="517f6-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-134">Optional.</span></span> <span data-ttu-id="517f6-135">Vea [Inherits (instrucción](../statements/inherits-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="517f6-135">See [Inherits Statement](../statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="517f6-136">Obligatorio si se usa `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="517f6-136">Required if you use `Inherits`.</span></span> <span data-ttu-id="517f6-137">El nombre de la clase o la interfaz de la que se deriva esta clase.</span><span class="sxs-lookup"><span data-stu-id="517f6-137">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="517f6-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-138">Optional.</span></span> <span data-ttu-id="517f6-139">Vea [Implements (instrucción](../statements/implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="517f6-139">See [Implements Statement](../statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="517f6-140">Obligatorio si se usa `Implements`.</span><span class="sxs-lookup"><span data-stu-id="517f6-140">Required if you use `Implements`.</span></span> <span data-ttu-id="517f6-141">Los nombres de las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-141">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="517f6-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-142">Optional.</span></span> <span data-ttu-id="517f6-143">Instrucciones que declaran variables adicionales y eventos para el tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-143">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="517f6-144">Opcional.</span><span class="sxs-lookup"><span data-stu-id="517f6-144">Optional.</span></span> <span data-ttu-id="517f6-145">Instrucciones que declaran y definen procedimientos adicionales para el tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-145">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="517f6-146">`End Class` o `End Structure`</span><span class="sxs-lookup"><span data-stu-id="517f6-146">`End Class` or `End Structure`</span></span>|<span data-ttu-id="517f6-147">Finaliza esta definición `Class` o `Structure` parcial.</span><span class="sxs-lookup"><span data-stu-id="517f6-147">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="517f6-148">Observaciones</span><span class="sxs-lookup"><span data-stu-id="517f6-148">Remarks</span></span>  

 <span data-ttu-id="517f6-149">Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes.</span><span class="sxs-lookup"><span data-stu-id="517f6-149">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="517f6-150">Por ejemplo, el **Diseñador de Windows Forms<xref:System.Windows.Forms.Form> define clases parciales para controles como**.</span><span class="sxs-lookup"><span data-stu-id="517f6-150">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="517f6-151">No debe modificar el código generado en estos controles.</span><span class="sxs-lookup"><span data-stu-id="517f6-151">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="517f6-152">Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.</span><span class="sxs-lookup"><span data-stu-id="517f6-152">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="517f6-153">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="517f6-153">Best Practices</span></span>  
  
- <span data-ttu-id="517f6-154">En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="517f6-154">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="517f6-155">Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="517f6-155">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="517f6-156">Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="517f6-156">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="517f6-157">El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.</span><span class="sxs-lookup"><span data-stu-id="517f6-157">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="517f6-158">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="517f6-158">Behavior</span></span>  
  
- <span data-ttu-id="517f6-159">**Unión de declaraciones.**</span><span class="sxs-lookup"><span data-stu-id="517f6-159">**Union of Declarations.**</span></span> <span data-ttu-id="517f6-160">El compilador trata el tipo como la unión de todas sus declaraciones parciales.</span><span class="sxs-lookup"><span data-stu-id="517f6-160">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="517f6-161">Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-161">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="517f6-162">**Promoción de tipos no permitida para los tipos parciales en los módulos.**</span><span class="sxs-lookup"><span data-stu-id="517f6-162">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="517f6-163">Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="517f6-163">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="517f6-164">En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="517f6-164">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="517f6-165">Para obtener más información, consulte [promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="517f6-165">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="517f6-166">El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.</span><span class="sxs-lookup"><span data-stu-id="517f6-166">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="517f6-167">La palabra clave `Partial` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="517f6-167">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="517f6-168">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="517f6-168">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="517f6-169">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="517f6-169">Structure Statement</span></span>](../statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="517f6-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="517f6-170">Example</span></span>  

 <span data-ttu-id="517f6-171">En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="517f6-171">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="517f6-172">Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.</span><span class="sxs-lookup"><span data-stu-id="517f6-172">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517f6-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="517f6-173">See also</span></span>

- [<span data-ttu-id="517f6-174">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="517f6-174">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="517f6-175">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="517f6-175">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="517f6-176">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="517f6-176">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="517f6-177">Shadows</span><span class="sxs-lookup"><span data-stu-id="517f6-177">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="517f6-178">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="517f6-178">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="517f6-179">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="517f6-179">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
