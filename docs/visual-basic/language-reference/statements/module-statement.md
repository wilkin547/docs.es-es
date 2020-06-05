---
title: Module (Instrucción)
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
ms.openlocfilehash: 24a27ba41f5ac889f2f2725a2852368a4292a6fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404464"
---
# <a name="module-statement"></a><span data-ttu-id="5cb42-102">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5cb42-102">Module Statement</span></span>

<span data-ttu-id="5cb42-103">Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que el módulo incluye.</span><span class="sxs-lookup"><span data-stu-id="5cb42-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cb42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cb42-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="5cb42-105">Partes</span><span class="sxs-lookup"><span data-stu-id="5cb42-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="5cb42-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5cb42-106">Optional.</span></span> <span data-ttu-id="5cb42-107">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-107">See [Attribute List](attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="5cb42-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5cb42-108">Optional.</span></span> <span data-ttu-id="5cb42-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cb42-109">Can be one of the following:</span></span>

- [<span data-ttu-id="5cb42-110">Público</span><span class="sxs-lookup"><span data-stu-id="5cb42-110">Public</span></span>](../modifiers/public.md)

- [<span data-ttu-id="5cb42-111">Respecto</span><span class="sxs-lookup"><span data-stu-id="5cb42-111">Friend</span></span>](../modifiers/friend.md)

<span data-ttu-id="5cb42-112">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-112">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="5cb42-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5cb42-113">Required.</span></span> <span data-ttu-id="5cb42-114">Nombre de este módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-114">Name of this module.</span></span> <span data-ttu-id="5cb42-115">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-115">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="5cb42-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5cb42-116">Optional.</span></span> <span data-ttu-id="5cb42-117">Instrucciones que definen las variables, propiedades, eventos, procedimientos y tipos anidados de este módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="5cb42-118">Termina la definición de `Module`.</span><span class="sxs-lookup"><span data-stu-id="5cb42-118">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cb42-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5cb42-119">Remarks</span></span>

<span data-ttu-id="5cb42-120">Una `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cb42-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="5cb42-121">Un *módulo* (a veces denominado *módulo estándar*) es similar a una clase, pero con algunas distinciones importantes.</span><span class="sxs-lookup"><span data-stu-id="5cb42-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="5cb42-122">Cada módulo tiene exactamente una instancia y no es necesario crearla o asignarla a una variable.</span><span class="sxs-lookup"><span data-stu-id="5cb42-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="5cb42-123">Los módulos no admiten la herencia ni implementan interfaces.</span><span class="sxs-lookup"><span data-stu-id="5cb42-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="5cb42-124">Observe que un módulo no es un *tipo* en el sentido de que una clase o estructura es: no puede declarar un elemento de programación para que tenga el tipo de datos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="5cb42-125">Solo se puede usar `Module` en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cb42-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="5cb42-126">Esto significa que el contexto de la *declaración* de un módulo debe ser un archivo de código fuente o un espacio de nombres, y no puede ser una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="5cb42-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="5cb42-127">No se puede anidar un módulo dentro de otro módulo o dentro de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="5cb42-128">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="5cb42-128">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="5cb42-129">Un módulo tiene la misma duración que el programa.</span><span class="sxs-lookup"><span data-stu-id="5cb42-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="5cb42-130">Como todos sus miembros `Shared` , también tienen una duración igual a la del programa.</span><span class="sxs-lookup"><span data-stu-id="5cb42-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="5cb42-131">El acceso predeterminado de los módulos es [Friend](../modifiers/friend.md) .</span><span class="sxs-lookup"><span data-stu-id="5cb42-131">Modules default to [Friend](../modifiers/friend.md) access.</span></span> <span data-ttu-id="5cb42-132">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="5cb42-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="5cb42-133">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-133">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="5cb42-134">Todos los miembros de un módulo son implícitamente `Shared` .</span><span class="sxs-lookup"><span data-stu-id="5cb42-134">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="5cb42-135">Clases y módulos</span><span class="sxs-lookup"><span data-stu-id="5cb42-135">Classes and Modules</span></span>

<span data-ttu-id="5cb42-136">Estos elementos tienen muchas similitudes, pero también hay algunas diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="5cb42-136">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="5cb42-137">**Terminología.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-137">**Terminology.**</span></span> <span data-ttu-id="5cb42-138">Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos. CLS) y *módulos estándar* (archivos. Bas).</span><span class="sxs-lookup"><span data-stu-id="5cb42-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="5cb42-139">La versión actual llama a estas *clases* y *módulos*, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5cb42-139">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="5cb42-140">**Miembros compartidos.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-140">**Shared Members.**</span></span> <span data-ttu-id="5cb42-141">Puede controlar si un miembro de una clase es un miembro compartido o de instancia.</span><span class="sxs-lookup"><span data-stu-id="5cb42-141">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="5cb42-142">**Orientación de objeto.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-142">**Object Orientation.**</span></span> <span data-ttu-id="5cb42-143">Las clases están orientadas a objetos, pero los módulos no lo son.</span><span class="sxs-lookup"><span data-stu-id="5cb42-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="5cb42-144">De modo que solo se pueden crear instancias de las clases como objetos.</span><span class="sxs-lookup"><span data-stu-id="5cb42-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="5cb42-145">Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-145">For more information, see [Objects and Classes](../../programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="5cb42-146">Reglas</span><span class="sxs-lookup"><span data-stu-id="5cb42-146">Rules</span></span>

- <span data-ttu-id="5cb42-147">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-147">**Modifiers.**</span></span> <span data-ttu-id="5cb42-148">Todos los miembros de módulo están [compartidos](../modifiers/shared.md)implícitamente.</span><span class="sxs-lookup"><span data-stu-id="5cb42-148">All module members are implicitly [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="5cb42-149">No se puede usar la `Shared` palabra clave al declarar un miembro y no se puede modificar el estado compartido de ningún miembro.</span><span class="sxs-lookup"><span data-stu-id="5cb42-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="5cb42-150">**Ella.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-150">**Inheritance.**</span></span> <span data-ttu-id="5cb42-151">Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object> , del que heredan todos los módulos.</span><span class="sxs-lookup"><span data-stu-id="5cb42-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="5cb42-152">En concreto, un módulo no puede heredar de otro.</span><span class="sxs-lookup"><span data-stu-id="5cb42-152">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="5cb42-153">No se puede usar la [instrucción Inherits](inherits-statement.md) en una definición de módulo, ni siquiera para especificar <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="5cb42-153">You cannot use the [Inherits Statement](inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="5cb42-154">**Propiedad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-154">**Default Property.**</span></span> <span data-ttu-id="5cb42-155">No se puede definir ninguna propiedad predeterminada en un módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="5cb42-156">Para obtener más información, vea [default](../modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-156">For more information, see [Default](../modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="5cb42-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="5cb42-157">Behavior</span></span>

- <span data-ttu-id="5cb42-158">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-158">**Access Level.**</span></span> <span data-ttu-id="5cb42-159">Dentro de un módulo, puede declarar cada miembro con su propio nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="5cb42-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="5cb42-160">Los miembros del módulo tienen acceso [público](../modifiers/public.md) de forma predeterminada, excepto las variables y constantes, que tienen como valor predeterminado el acceso [privado](../modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="5cb42-160">Module members default to [Public](../modifiers/public.md) access, except variables and constants, which default to [Private](../modifiers/private.md) access.</span></span> <span data-ttu-id="5cb42-161">Cuando un módulo tiene más acceso restringido que uno de sus miembros, tiene prioridad el nivel de acceso del módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="5cb42-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="5cb42-162">**Ámbito.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-162">**Scope.**</span></span> <span data-ttu-id="5cb42-163">Un módulo está en el ámbito A lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cb42-163">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="5cb42-164">El ámbito de cada miembro del módulo es todo el módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="5cb42-165">Observe que todos los miembros se someten a la *promoción de tipos*, lo que hace que su ámbito se promueva al espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="5cb42-166">Para obtener más información, consulte [promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-166">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="5cb42-167">**Evaluación.**</span><span class="sxs-lookup"><span data-stu-id="5cb42-167">**Qualification.**</span></span> <span data-ttu-id="5cb42-168">Puede tener varios módulos en un proyecto y puede declarar miembros con el mismo nombre en dos o más módulos.</span><span class="sxs-lookup"><span data-stu-id="5cb42-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="5cb42-169">Sin embargo, debe calificar cualquier referencia a este miembro con el nombre de módulo adecuado si la referencia es de fuera de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="5cb42-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="5cb42-170">Para obtener más información, consulta [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="5cb42-170">For more information, see [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="5cb42-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cb42-171">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="5cb42-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5cb42-172">See also</span></span>

- [<span data-ttu-id="5cb42-173">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="5cb42-173">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="5cb42-174">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5cb42-174">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="5cb42-175">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5cb42-175">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="5cb42-176">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="5cb42-176">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="5cb42-177">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5cb42-177">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="5cb42-178">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="5cb42-178">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
