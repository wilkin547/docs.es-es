---
title: Lista de tipos (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605295"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="afced-102">Lista de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afced-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="afced-103">Especifica la *parámetros de tipo* para un *genérico* elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="afced-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="afced-104">Varios parámetros se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="afced-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="afced-105">A continuación se muestra la sintaxis para un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="afced-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afced-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afced-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="afced-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="afced-107">Parts</span></span>  
  
|<span data-ttu-id="afced-108">Término</span><span class="sxs-lookup"><span data-stu-id="afced-108">Term</span></span>|<span data-ttu-id="afced-109">Definición</span><span class="sxs-lookup"><span data-stu-id="afced-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="afced-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="afced-110">Optional.</span></span> <span data-ttu-id="afced-111">Puede usarse solo en interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="afced-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="afced-112">Puede declarar un tipo covariante mediante la [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) palabra clave o contravariante utilizando la [en](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="afced-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="afced-113">Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="afced-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="afced-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="afced-114">Required.</span></span> <span data-ttu-id="afced-115">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="afced-115">Name of the type parameter.</span></span> <span data-ttu-id="afced-116">Se trata de un marcador de posición, que será sustituido por un tipo definido proporcionado por el argumento de tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="afced-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="afced-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="afced-117">Optional.</span></span> <span data-ttu-id="afced-118">Lista de requisitos que restringe el tipo de datos que se pueden proporcionar para `typename`.</span><span class="sxs-lookup"><span data-stu-id="afced-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="afced-119">Si tiene varias restricciones, encierre entre llaves (`{ }`) y sepárelas con comas.</span><span class="sxs-lookup"><span data-stu-id="afced-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="afced-120">Debe introducir la lista de restricciones con la [como](../../../visual-basic/language-reference/statements/as-clause.md) (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="afced-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="afced-121">Usa `As` una sola vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="afced-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afced-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afced-122">Remarks</span></span>  
 <span data-ttu-id="afced-123">Cada elemento de programación genérico debe tomar al menos un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="afced-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="afced-124">Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="afced-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="afced-125">Puede definir una clase genérica, estructura, interfaz, procedimiento o delegado.</span><span class="sxs-lookup"><span data-stu-id="afced-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="afced-126">Para obtener más información sobre cuándo se debe definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="afced-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="afced-127">Para obtener más información sobre nombres de parámetros de tipo, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="afced-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="afced-128">Reglas</span><span class="sxs-lookup"><span data-stu-id="afced-128">Rules</span></span>  
  
-   <span data-ttu-id="afced-129">**Paréntesis.**</span><span class="sxs-lookup"><span data-stu-id="afced-129">**Parentheses.**</span></span> <span data-ttu-id="afced-130">Si se proporciona una lista de parámetros de tipo, debe encerrarlo entre paréntesis y debe introducir la lista con el [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="afced-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="afced-131">Usa `Of` una sola vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="afced-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="afced-132">**Restricciones.**</span><span class="sxs-lookup"><span data-stu-id="afced-132">**Constraints.**</span></span> <span data-ttu-id="afced-133">Una lista de *restricciones* en un tipo de parámetro puede incluir los elementos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="afced-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="afced-134">Cualquier número de interfaces.</span><span class="sxs-lookup"><span data-stu-id="afced-134">Any number of interfaces.</span></span> <span data-ttu-id="afced-135">El tipo proporcionado debe implementar cada interfaz en esta lista.</span><span class="sxs-lookup"><span data-stu-id="afced-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="afced-136">Al menos una clase.</span><span class="sxs-lookup"><span data-stu-id="afced-136">At most one class.</span></span> <span data-ttu-id="afced-137">El tipo proporcionado debe heredar de esa clase.</span><span class="sxs-lookup"><span data-stu-id="afced-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="afced-138">Palabra clave `New`.</span><span class="sxs-lookup"><span data-stu-id="afced-138">The `New` keyword.</span></span> <span data-ttu-id="afced-139">El tipo proporcionado debe exponer un constructor sin parámetros al que puede tener acceso su tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="afced-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="afced-140">Esto es útil si restringe un parámetro de tipo por una o varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="afced-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="afced-141">Un tipo que implementa las interfaces no expone necesariamente un constructor, y según el nivel de acceso de un constructor, el código dentro del tipo genérico no pueda tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="afced-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="afced-142">Ya sea la `Class` palabra clave o el `Structure` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="afced-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="afced-143">El `Class` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la sea un tipo de referencia, por ejemplo una cadena, matriz o delegado, o un objeto creado a partir de una clase.</span><span class="sxs-lookup"><span data-stu-id="afced-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="afced-144">El `Structure` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la sea un tipo de valor, por ejemplo una estructura, enumeración o datos elementales escriba.</span><span class="sxs-lookup"><span data-stu-id="afced-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="afced-145">No se puede incluir tanto `Class` y `Structure` en el mismo `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="afced-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="afced-146">El tipo proporcionado debe satisfacer cada requisito que se incluya en `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="afced-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="afced-147">Restricciones de cada parámetro de tipo son independientes de las restricciones de otros tipos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="afced-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="afced-148">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="afced-148">Behavior</span></span>  
  
-   <span data-ttu-id="afced-149">**Sustitución de tiempo de compilación.**</span><span class="sxs-lookup"><span data-stu-id="afced-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="afced-150">Cuando se crea un tipo construido de un elemento de programación genérico, proporciona un tipo definido para cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="afced-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="afced-151">El compilador de Visual Basic sustituye el tipo proporcionado para todas las apariciones de `typename` dentro del elemento genérico.</span><span class="sxs-lookup"><span data-stu-id="afced-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="afced-152">**Si no existen restricciones.**</span><span class="sxs-lookup"><span data-stu-id="afced-152">**Absence of Constraints.**</span></span> <span data-ttu-id="afced-153">Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y los miembros admitidos por el [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) para ese parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="afced-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afced-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afced-154">Example</span></span>  
 <span data-ttu-id="afced-155">En el ejemplo siguiente se muestra un esquema de definición de una clase de diccionario genérico, incluida una función esquemática para agregar una nueva entrada al diccionario.</span><span class="sxs-lookup"><span data-stu-id="afced-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="afced-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afced-156">Example</span></span>  
 <span data-ttu-id="afced-157">Dado que `dictionary` es genérico, el código que lo usa puede crear una variedad de objetos del mismo, cada uno tiene la misma funcionalidad pero que actúa en un tipo de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="afced-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="afced-158">En el ejemplo siguiente se muestra una línea de código que crea un `dictionary` objeto con `String` entradas y `Integer` claves.</span><span class="sxs-lookup"><span data-stu-id="afced-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="afced-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afced-159">Example</span></span>  
 <span data-ttu-id="afced-160">En el ejemplo siguiente se muestra el esquema de definición equivalente generado por el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="afced-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="afced-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="afced-161">See Also</span></span>  
 [<span data-ttu-id="afced-162">Of</span><span class="sxs-lookup"><span data-stu-id="afced-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="afced-163">New (operador)</span><span class="sxs-lookup"><span data-stu-id="afced-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="afced-164">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afced-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="afced-165">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="afced-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="afced-166">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="afced-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="afced-167">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="afced-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="afced-168">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="afced-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="afced-169">Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="afced-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="afced-170">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="afced-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="afced-171">In</span><span class="sxs-lookup"><span data-stu-id="afced-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="afced-172">Out</span><span class="sxs-lookup"><span data-stu-id="afced-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
