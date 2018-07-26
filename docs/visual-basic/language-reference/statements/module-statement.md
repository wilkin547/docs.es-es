---
title: Module (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244106"
---
# <a name="module-statement"></a><span data-ttu-id="340bb-102">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-102">Module Statement</span></span>
<span data-ttu-id="340bb-103">Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que incluye el módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="340bb-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="340bb-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="340bb-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="340bb-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="340bb-106">Optional.</span></span> <span data-ttu-id="340bb-107">Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="340bb-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="340bb-108">Optional.</span></span> <span data-ttu-id="340bb-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="340bb-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="340bb-110">Public</span><span class="sxs-lookup"><span data-stu-id="340bb-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="340bb-111">Friend</span><span class="sxs-lookup"><span data-stu-id="340bb-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="340bb-112">Consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="340bb-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="340bb-113">Required.</span></span> <span data-ttu-id="340bb-114">Nombre de este módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-114">Name of this module.</span></span> <span data-ttu-id="340bb-115">Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="340bb-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="340bb-116">Optional.</span></span> <span data-ttu-id="340bb-117">Instrucciones que definen las variables, propiedades, eventos, procedimientos y los tipos anidados de este módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="340bb-118">Termina la definición de `Module`.</span><span class="sxs-lookup"><span data-stu-id="340bb-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="340bb-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="340bb-119">Remarks</span></span>  
 <span data-ttu-id="340bb-120">Un `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="340bb-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="340bb-121">Un *módulo* (a veces denominado un *módulo estándar*) es similar a una clase, pero con algunas diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="340bb-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="340bb-122">Cada módulo tiene exactamente una instancia y no necesita ser creado ni asignado a una variable.</span><span class="sxs-lookup"><span data-stu-id="340bb-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="340bb-123">Los módulos no admiten la herencia ni implementan interfaces.</span><span class="sxs-lookup"><span data-stu-id="340bb-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="340bb-124">Tenga en cuenta que un módulo no es un *tipo* en el sentido de que es una clase o estructura, no se puede declarar un elemento de programación para que el tipo de datos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="340bb-125">Puede usar `Module` sólo en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="340bb-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="340bb-126">Esto significa que el *contexto de declaración* para un módulo debe ser un archivo de código fuente o espacio de nombres y no puede ser la clase, estructura, módulo, interfaz, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="340bb-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="340bb-127">No se puede anidar un módulo dentro de otro módulo, o dentro de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="340bb-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="340bb-128">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="340bb-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="340bb-129">Un módulo tiene la misma duración que el programa.</span><span class="sxs-lookup"><span data-stu-id="340bb-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="340bb-130">Dado que sus miembros son todos `Shared`, también tienen duraciones iguales que el del programa.</span><span class="sxs-lookup"><span data-stu-id="340bb-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="340bb-131">De forma predeterminada los módulos [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso.</span><span class="sxs-lookup"><span data-stu-id="340bb-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="340bb-132">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="340bb-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="340bb-133">Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="340bb-134">Todos los miembros de un módulo son implícitamente `Shared`.</span><span class="sxs-lookup"><span data-stu-id="340bb-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="340bb-135">Las clases y módulos</span><span class="sxs-lookup"><span data-stu-id="340bb-135">Classes and Modules</span></span>  
 <span data-ttu-id="340bb-136">Estos elementos tienen muchas similitudes, pero hay diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="340bb-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="340bb-137">**Terminología.**</span><span class="sxs-lookup"><span data-stu-id="340bb-137">**Terminology.**</span></span> <span data-ttu-id="340bb-138">Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos .cls) y *módulos estándar* (archivos BAS).</span><span class="sxs-lookup"><span data-stu-id="340bb-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="340bb-139">La versión actual llama a estos *clases* y *módulos*, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="340bb-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="340bb-140">**Miembros compartidos.**</span><span class="sxs-lookup"><span data-stu-id="340bb-140">**Shared Members.**</span></span> <span data-ttu-id="340bb-141">Puede controlar si un miembro de una clase es un compartido o un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="340bb-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="340bb-142">**Orientación a objetos.**</span><span class="sxs-lookup"><span data-stu-id="340bb-142">**Object Orientation.**</span></span> <span data-ttu-id="340bb-143">Clases están orientada a objetos, pero no son de módulos.</span><span class="sxs-lookup"><span data-stu-id="340bb-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="340bb-144">Por lo que se pueden crear instancias únicas clases como objetos.</span><span class="sxs-lookup"><span data-stu-id="340bb-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="340bb-145">Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="340bb-146">Reglas</span><span class="sxs-lookup"><span data-stu-id="340bb-146">Rules</span></span>  
  
-   <span data-ttu-id="340bb-147">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="340bb-147">**Modifiers.**</span></span> <span data-ttu-id="340bb-148">Todos los miembros de módulo son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="340bb-149">No puede usar el `Shared` palabra clave al declarar un miembro y no puede modificar el estado de cualquier miembro compartido.</span><span class="sxs-lookup"><span data-stu-id="340bb-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="340bb-150">**Herencia.**</span><span class="sxs-lookup"><span data-stu-id="340bb-150">**Inheritance.**</span></span> <span data-ttu-id="340bb-151">Un módulo no puede heredar de ningún tipo distinto <xref:System.Object>, todos los módulos heredan.</span><span class="sxs-lookup"><span data-stu-id="340bb-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="340bb-152">En concreto, un módulo no puede heredar de otra.</span><span class="sxs-lookup"><span data-stu-id="340bb-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="340bb-153">No puede usar el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de módulo, ni siquiera para especificar <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="340bb-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="340bb-154">**Propiedad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="340bb-154">**Default Property.**</span></span> <span data-ttu-id="340bb-155">No se puede definir cualquier propiedad predeterminada en un módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="340bb-156">Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="340bb-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="340bb-157">Behavior</span></span>  
  
-   <span data-ttu-id="340bb-158">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="340bb-158">**Access Level.**</span></span> <span data-ttu-id="340bb-159">Dentro de un módulo, puede declarar a cada miembro con su propio nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="340bb-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="340bb-160">De forma predeterminada los miembros del módulo [pública](../../../visual-basic/language-reference/modifiers/public.md) acceder, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso.</span><span class="sxs-lookup"><span data-stu-id="340bb-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="340bb-161">Cuando un módulo con más acceso restringido que uno de sus miembros, el nivel de acceso del módulo especificado tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="340bb-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="340bb-162">**Ámbito.**</span><span class="sxs-lookup"><span data-stu-id="340bb-162">**Scope.**</span></span> <span data-ttu-id="340bb-163">Es un módulo en el ámbito de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="340bb-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="340bb-164">El ámbito de todos los miembros del módulo es el módulo completo.</span><span class="sxs-lookup"><span data-stu-id="340bb-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="340bb-165">Tenga en cuenta que todos los miembros se someten a *promoción*, lo que hace que su ámbito se promueva al nivel de espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="340bb-166">Para obtener más información, consulte [promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="340bb-167">**Calificación.**</span><span class="sxs-lookup"><span data-stu-id="340bb-167">**Qualification.**</span></span> <span data-ttu-id="340bb-168">Puede tener varios módulos en un proyecto y puede declarar a miembros con el mismo nombre en dos o más módulos.</span><span class="sxs-lookup"><span data-stu-id="340bb-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="340bb-169">Sin embargo, debe calificar cualquier referencia a este miembro con el nombre de módulo correspondiente si la referencia es de fuera de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="340bb-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="340bb-170">Para obtener más información, consulte [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="340bb-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="340bb-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="340bb-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="340bb-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="340bb-172">See Also</span></span>  
 [<span data-ttu-id="340bb-173">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="340bb-174">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="340bb-175">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="340bb-176">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="340bb-177">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="340bb-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="340bb-178">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="340bb-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
