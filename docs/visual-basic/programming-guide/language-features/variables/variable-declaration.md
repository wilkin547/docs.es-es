---
description: 'Más información sobre: Declaración de variables en Visual Basic'
title: Declaración de variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: ef0e7bc7a99f320bd40788ef019b05c7ebf4ce46
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462703"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="fa2bf-103">Declaración de variable en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa2bf-103">Variable Declaration in Visual Basic</span></span>

<span data-ttu-id="fa2bf-104">Declare una variable para especificar su nombre y sus características.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-104">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="fa2bf-105">La instrucción de declaración para variables es la [instrucción Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-105">The declaration statement for variables is the [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="fa2bf-106">Su ubicación y contenido determinan las características de la variable.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-106">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="fa2bf-107">Para conocer las reglas y consideraciones de nomenclatura de variables, vea [nombres de elementos declarados](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-107">For variable naming rules and considerations, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="fa2bf-108">Niveles de declaración</span><span class="sxs-lookup"><span data-stu-id="fa2bf-108">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="fa2bf-109">Variables locales y de miembro</span><span class="sxs-lookup"><span data-stu-id="fa2bf-109">Local and Member Variables</span></span>  

 <span data-ttu-id="fa2bf-110">Una *variable local* es aquella que se declara dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-110">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="fa2bf-111">Una *variable miembro* es miembro de un tipo de Visual Basic; se declara en el nivel de módulo, dentro de una clase, estructura o módulo, pero no dentro de ningún procedimiento interno de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-111">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="fa2bf-112">Variables compartidas y de instancia</span><span class="sxs-lookup"><span data-stu-id="fa2bf-112">Shared and Instance Variables</span></span>  

 <span data-ttu-id="fa2bf-113">En una clase o estructura, la categoría de una variable miembro depende de si es o no compartida.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-113">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="fa2bf-114">Si se declara con la palabra clave [Shared](../../../language-reference/modifiers/shared.md) , es una *variable compartida* y existe en una sola copia compartida entre todas las instancias de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-114">If it is declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="fa2bf-115">En caso contrario, es una *variable de instancia* y se crea una copia independiente de la misma para cada instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-115">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="fa2bf-116">Una copia determinada de una variable de instancia solo está disponible para la instancia de la clase o estructura en la que se creó.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-116">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="fa2bf-117">Es independiente de una copia de la variable de instancia en cualquier otra instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-117">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="fa2bf-118">Declarar el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fa2bf-118">Declaring Data Type</span></span>  

 <span data-ttu-id="fa2bf-119">La cláusula [as](../../../language-reference/statements/as-clause.md) de la instrucción de declaración permite definir el tipo de datos o el tipo de objeto de la variable que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-119">The [As](../../../language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="fa2bf-120">Puede especificar cualquiera de los siguientes tipos para una variable:</span><span class="sxs-lookup"><span data-stu-id="fa2bf-120">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="fa2bf-121">Un tipo de datos elemental, como `Boolean` , `Long` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="fa2bf-121">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="fa2bf-122">Un tipo de datos compuesto, como una matriz o una estructura</span><span class="sxs-lookup"><span data-stu-id="fa2bf-122">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="fa2bf-123">Un tipo de objeto, o clase, definido en la aplicación o en otra aplicación</span><span class="sxs-lookup"><span data-stu-id="fa2bf-123">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="fa2bf-124">Una clase .NET Framework, como <xref:System.Windows.Forms.Label> o. <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="fa2bf-124">A .NET Framework class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="fa2bf-125">Un tipo de interfaz, como <xref:System.IComparable> o. <xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="fa2bf-125">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="fa2bf-126">Puede declarar varias variables en una instrucción sin tener que repetir el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-126">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="fa2bf-127">En las siguientes instrucciones, las variables `i` , `j` y `k` se declaran como de tipo `Integer` , `l` y `m` como `Long` , y `x` y `y` como `Single` :</span><span class="sxs-lookup"><span data-stu-id="fa2bf-127">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="fa2bf-128">Para obtener más información sobre los tipos de datos, vea [tipos de datos](../data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-128">For more information on data types, see [Data Types](../data-types/index.md).</span></span> <span data-ttu-id="fa2bf-129">Para obtener más información sobre los objetos, vea [objetos y clases](../objects-and-classes/index.md) y [programación con componentes](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-129">For more information on objects, see [Objects and Classes](../objects-and-classes/index.md) and [Programming with Components](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="fa2bf-130">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="fa2bf-130">Local Type Inference</span></span>  

 <span data-ttu-id="fa2bf-131">La *inferencia de tipos* se usa para determinar los tipos de datos de las variables locales declaradas sin una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-131">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="fa2bf-132">El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-132">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="fa2bf-133">Esto le permite declarar variables sin indicar explícitamente un tipo.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-133">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="fa2bf-134">En el ejemplo siguiente, `num1` y `num2` están fuertemente tipados como enteros.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-134">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="fa2bf-135">Si desea utilizar la inferencia de tipo de local, `Option Infer` debe establecerse en `On` .</span><span class="sxs-lookup"><span data-stu-id="fa2bf-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="fa2bf-136">Para obtener más información, vea [Local Type Inference](local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-136">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="fa2bf-137">Características de las variables declaradas</span><span class="sxs-lookup"><span data-stu-id="fa2bf-137">Characteristics of Declared Variables</span></span>  

 <span data-ttu-id="fa2bf-138">La *duración* de una variable es el período de tiempo durante el cual está disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="fa2bf-139">En general, existe una variable siempre que el elemento que la declara (por ejemplo, un procedimiento o una clase) sigue existiendo.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="fa2bf-140">Si la variable no necesita continuar ya existente más allá de la duración de su elemento contenedor, no es necesario hacer nada especial en la declaración.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="fa2bf-141">Si la variable debe seguir existiendo más tiempo que su elemento contenedor, puede incluir la `Static` `Shared` palabra clave o en su `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="fa2bf-142">Para obtener más información, vea [duración en Visual Basic](../declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-142">For more information, see [Lifetime in Visual Basic](../declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="fa2bf-143">El *ámbito* de una variable es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="fa2bf-144">El ámbito de una variable lo determina el lugar en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="fa2bf-145">El código ubicado en una región determinada puede usar las variables definidas en esa región sin tener que calificar sus nombres.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="fa2bf-146">Para obtener más información, consulta [Scope in Visual Basic](../declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-146">For more information, see [Scope in Visual Basic](../declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="fa2bf-147">El nivel de *acceso* de una variable es la extensión del código que tiene permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="fa2bf-148">Esto viene determinado por el modificador de acceso (por ejemplo, [público](../../../language-reference/modifiers/public.md) o [privado](../../../language-reference/modifiers/private.md)) que se usa en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="fa2bf-148">This is determined by the access modifier (such as [Public](../../../language-reference/modifiers/public.md) or [Private](../../../language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="fa2bf-149">Para obtener más información, consulte [niveles de acceso en Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bf-149">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2bf-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa2bf-150">See also</span></span>

- [<span data-ttu-id="fa2bf-151">Procedimiento para crear una variable</span><span class="sxs-lookup"><span data-stu-id="fa2bf-151">How to: Create a New Variable</span></span>](how-to-create-a-new-variable.md)
- [<span data-ttu-id="fa2bf-152">Procedimiento para introducir y extraer los datos de una variable</span><span class="sxs-lookup"><span data-stu-id="fa2bf-152">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="fa2bf-153">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fa2bf-153">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="fa2bf-154">Protegido</span><span class="sxs-lookup"><span data-stu-id="fa2bf-154">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="fa2bf-155">Friend</span><span class="sxs-lookup"><span data-stu-id="fa2bf-155">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="fa2bf-156">Estática</span><span class="sxs-lookup"><span data-stu-id="fa2bf-156">Static</span></span>](../../../language-reference/modifiers/static.md)
- [<span data-ttu-id="fa2bf-157">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="fa2bf-157">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="fa2bf-158">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="fa2bf-158">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="fa2bf-159">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fa2bf-159">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
