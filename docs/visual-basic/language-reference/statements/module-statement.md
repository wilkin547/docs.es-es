---
title: "Module (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a><span data-ttu-id="c977d-102">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-102">Module Statement</span></span>
<span data-ttu-id="c977d-103">Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y los procedimientos que incluye el módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c977d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c977d-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="c977d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c977d-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="c977d-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c977d-106">Optional.</span></span> <span data-ttu-id="c977d-107">Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="c977d-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c977d-108">Optional.</span></span> <span data-ttu-id="c977d-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c977d-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="c977d-110">Public</span><span class="sxs-lookup"><span data-stu-id="c977d-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="c977d-111">Friend</span><span class="sxs-lookup"><span data-stu-id="c977d-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="c977d-112">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="c977d-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c977d-113">Required.</span></span> <span data-ttu-id="c977d-114">Nombre de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-114">Name of this module.</span></span> <span data-ttu-id="c977d-115">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="c977d-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c977d-116">Optional.</span></span> <span data-ttu-id="c977d-117">Instrucciones que definen las variables, propiedades, eventos, procedimientos y los tipos anidados de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="c977d-118">Termina la definición de `Module`.</span><span class="sxs-lookup"><span data-stu-id="c977d-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c977d-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c977d-119">Remarks</span></span>  
 <span data-ttu-id="c977d-120">Un `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c977d-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="c977d-121">A *módulo* (a veces denominado un *módulo estándar*) es similar a una clase pero con algunas diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="c977d-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="c977d-122">Cada módulo tiene exactamente una instancia y no necesita ser creado ni asignado a una variable.</span><span class="sxs-lookup"><span data-stu-id="c977d-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="c977d-123">Los módulos no admiten la herencia ni implementan interfaces.</span><span class="sxs-lookup"><span data-stu-id="c977d-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="c977d-124">Tenga en cuenta que un módulo no es un *tipo* en el sentido de que es una clase o estructura, no puede declarar un elemento de programación que el tipo de datos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="c977d-125">Puede usar `Module` en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c977d-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="c977d-126">Esto significa que la *contexto de la declaración* para un módulo debe ser un archivo de código fuente o espacio de nombres y no puede ser una clase, estructura, módulo, interfaz, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="c977d-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="c977d-127">No se pueden anidar un módulo dentro de otro módulo, o dentro de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="c977d-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="c977d-128">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="c977d-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="c977d-129">Un módulo tiene la misma duración que el programa.</span><span class="sxs-lookup"><span data-stu-id="c977d-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="c977d-130">Dado que sus miembros son todos los `Shared`, también tienen duraciones iguales que el programa.</span><span class="sxs-lookup"><span data-stu-id="c977d-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="c977d-131">De forma predeterminada los módulos [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso.</span><span class="sxs-lookup"><span data-stu-id="c977d-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="c977d-132">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="c977d-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="c977d-133">Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="c977d-134">Todos los miembros de un módulo son implícitamente `Shared`.</span><span class="sxs-lookup"><span data-stu-id="c977d-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="c977d-135">Las clases y módulos</span><span class="sxs-lookup"><span data-stu-id="c977d-135">Classes and Modules</span></span>  
 <span data-ttu-id="c977d-136">Estos elementos tienen muchas similitudes, pero hay diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="c977d-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="c977d-137">**Terminología.**</span><span class="sxs-lookup"><span data-stu-id="c977d-137">**Terminology.**</span></span> <span data-ttu-id="c977d-138">Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos de CLS) y *módulos estándar* (archivos de BAS).</span><span class="sxs-lookup"><span data-stu-id="c977d-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="c977d-139">La versión actual llama a estos *clases* y *módulos*, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c977d-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="c977d-140">**Miembros compartidos.**</span><span class="sxs-lookup"><span data-stu-id="c977d-140">**Shared Members.**</span></span> <span data-ttu-id="c977d-141">Puede controlar si un miembro de una clase es un compartido o miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="c977d-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="c977d-142">**Orientación a objetos.**</span><span class="sxs-lookup"><span data-stu-id="c977d-142">**Object Orientation.**</span></span> <span data-ttu-id="c977d-143">Clases están orientada a objetos, pero no son de módulos.</span><span class="sxs-lookup"><span data-stu-id="c977d-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="c977d-144">Por lo que pueden crearse instancias de clases sola como objetos.</span><span class="sxs-lookup"><span data-stu-id="c977d-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="c977d-145">Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c977d-146">Reglas</span><span class="sxs-lookup"><span data-stu-id="c977d-146">Rules</span></span>  
  
-   <span data-ttu-id="c977d-147">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="c977d-147">**Modifiers.**</span></span> <span data-ttu-id="c977d-148">Todos los miembros de módulo son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="c977d-149">No se puede utilizar el `Shared` palabra clave al declarar un miembro y no puede modificar el estado de cualquier miembro compartido.</span><span class="sxs-lookup"><span data-stu-id="c977d-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="c977d-150">**Herencia.**</span><span class="sxs-lookup"><span data-stu-id="c977d-150">**Inheritance.**</span></span> <span data-ttu-id="c977d-151">Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object>, de que todos los módulos se heredan.</span><span class="sxs-lookup"><span data-stu-id="c977d-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="c977d-152">En concreto, un módulo no puede heredar de otra.</span><span class="sxs-lookup"><span data-stu-id="c977d-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="c977d-153">No se puede utilizar el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de módulo, incluso para especificar <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c977d-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="c977d-154">**Propiedad Default.**</span><span class="sxs-lookup"><span data-stu-id="c977d-154">**Default Property.**</span></span> <span data-ttu-id="c977d-155">No se puede definir las propiedades predeterminadas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="c977d-156">Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c977d-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="c977d-157">Behavior</span></span>  
  
-   <span data-ttu-id="c977d-158">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="c977d-158">**Access Level.**</span></span> <span data-ttu-id="c977d-159">Dentro de un módulo, puede declarar a cada miembro con su propio nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="c977d-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="c977d-160">De forma predeterminada los miembros de módulo [público](../../../visual-basic/language-reference/modifiers/public.md) tener acceso, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso.</span><span class="sxs-lookup"><span data-stu-id="c977d-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="c977d-161">Cuando un módulo más restringió el acceso a uno de sus miembros, el nivel de acceso del módulo especificado tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="c977d-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="c977d-162">**Ámbito.**</span><span class="sxs-lookup"><span data-stu-id="c977d-162">**Scope.**</span></span> <span data-ttu-id="c977d-163">Es un módulo en el ámbito de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c977d-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="c977d-164">El ámbito de cada miembro de módulo es el módulo completo.</span><span class="sxs-lookup"><span data-stu-id="c977d-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="c977d-165">Tenga en cuenta que todos los miembros se someten a *promoción de tipo*, lo que hace que su ámbito se promueva al espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="c977d-166">Para obtener más información, consulte [la promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="c977d-167">**Calificación.**</span><span class="sxs-lookup"><span data-stu-id="c977d-167">**Qualification.**</span></span> <span data-ttu-id="c977d-168">Puede tener varios módulos en un proyecto y puede declarar a miembros con el mismo nombre en dos o más módulos.</span><span class="sxs-lookup"><span data-stu-id="c977d-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="c977d-169">Sin embargo, debe calificar cualquier referencia a un miembro de este tipo con el nombre del módulo adecuado si la referencia es desde fuera de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="c977d-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="c977d-170">Para obtener más información, consulte [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="c977d-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c977d-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c977d-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c977d-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="c977d-172">See Also</span></span>  
 [<span data-ttu-id="c977d-173">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="c977d-174">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="c977d-175">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="c977d-176">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="c977d-177">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c977d-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c977d-178">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="c977d-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
