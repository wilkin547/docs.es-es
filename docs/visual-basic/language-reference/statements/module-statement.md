---
description: 'Más información acerca de: Module (instrucción)'
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
ms.openlocfilehash: 2a19bcfa4521d34b5a91fbc9de412a6d8f6f39c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768875"
---
# <a name="module-statement"></a><span data-ttu-id="514ef-103">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="514ef-103">Module Statement</span></span>

<span data-ttu-id="514ef-104">Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que el módulo incluye.</span><span class="sxs-lookup"><span data-stu-id="514ef-104">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="514ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="514ef-105">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="514ef-106">Partes</span><span class="sxs-lookup"><span data-stu-id="514ef-106">Parts</span></span>

`attributelist`  
<span data-ttu-id="514ef-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="514ef-107">Optional.</span></span> <span data-ttu-id="514ef-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-108">See [Attribute List](attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="514ef-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="514ef-109">Optional.</span></span> <span data-ttu-id="514ef-110">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="514ef-110">Can be one of the following:</span></span>

- [<span data-ttu-id="514ef-111">Público</span><span class="sxs-lookup"><span data-stu-id="514ef-111">Public</span></span>](../modifiers/public.md)

- [<span data-ttu-id="514ef-112">Friend</span><span class="sxs-lookup"><span data-stu-id="514ef-112">Friend</span></span>](../modifiers/friend.md)

<span data-ttu-id="514ef-113">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-113">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="514ef-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="514ef-114">Required.</span></span> <span data-ttu-id="514ef-115">Nombre de este módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-115">Name of this module.</span></span> <span data-ttu-id="514ef-116">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-116">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="514ef-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="514ef-117">Optional.</span></span> <span data-ttu-id="514ef-118">Instrucciones que definen las variables, propiedades, eventos, procedimientos y tipos anidados de este módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-118">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="514ef-119">Termina la definición de `Module`.</span><span class="sxs-lookup"><span data-stu-id="514ef-119">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="514ef-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="514ef-120">Remarks</span></span>

<span data-ttu-id="514ef-121">Una `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="514ef-121">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="514ef-122">Un *módulo* (a veces denominado *módulo estándar*) es similar a una clase, pero con algunas distinciones importantes.</span><span class="sxs-lookup"><span data-stu-id="514ef-122">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="514ef-123">Cada módulo tiene exactamente una instancia y no es necesario crearla o asignarla a una variable.</span><span class="sxs-lookup"><span data-stu-id="514ef-123">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="514ef-124">Los módulos no admiten la herencia ni implementan interfaces.</span><span class="sxs-lookup"><span data-stu-id="514ef-124">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="514ef-125">Observe que un módulo no es un *tipo* en el sentido de que una clase o estructura es: no puede declarar un elemento de programación para que tenga el tipo de datos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-125">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="514ef-126">Solo se puede usar `Module` en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="514ef-126">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="514ef-127">Esto significa que el contexto de la *declaración* de un módulo debe ser un archivo de código fuente o un espacio de nombres, y no puede ser una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="514ef-127">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="514ef-128">No se puede anidar un módulo dentro de otro módulo o dentro de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="514ef-128">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="514ef-129">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="514ef-129">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="514ef-130">Un módulo tiene la misma duración que el programa.</span><span class="sxs-lookup"><span data-stu-id="514ef-130">A module has the same lifetime as your program.</span></span> <span data-ttu-id="514ef-131">Como todos sus miembros `Shared` , también tienen una duración igual a la del programa.</span><span class="sxs-lookup"><span data-stu-id="514ef-131">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="514ef-132">El acceso predeterminado de los módulos es [Friend](../modifiers/friend.md) .</span><span class="sxs-lookup"><span data-stu-id="514ef-132">Modules default to [Friend](../modifiers/friend.md) access.</span></span> <span data-ttu-id="514ef-133">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="514ef-133">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="514ef-134">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-134">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="514ef-135">Todos los miembros de un módulo son implícitamente `Shared` .</span><span class="sxs-lookup"><span data-stu-id="514ef-135">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="514ef-136">Clases y módulos</span><span class="sxs-lookup"><span data-stu-id="514ef-136">Classes and Modules</span></span>

<span data-ttu-id="514ef-137">Estos elementos tienen muchas similitudes, pero también hay algunas diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="514ef-137">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="514ef-138">**Terminología.**</span><span class="sxs-lookup"><span data-stu-id="514ef-138">**Terminology.**</span></span> <span data-ttu-id="514ef-139">Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos. CLS) y *módulos estándar* (archivos. Bas).</span><span class="sxs-lookup"><span data-stu-id="514ef-139">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="514ef-140">La versión actual llama a estas *clases* y *módulos*, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="514ef-140">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="514ef-141">**Miembros compartidos.**</span><span class="sxs-lookup"><span data-stu-id="514ef-141">**Shared Members.**</span></span> <span data-ttu-id="514ef-142">Puede controlar si un miembro de una clase es un miembro compartido o de instancia.</span><span class="sxs-lookup"><span data-stu-id="514ef-142">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="514ef-143">**Orientación de objeto.**</span><span class="sxs-lookup"><span data-stu-id="514ef-143">**Object Orientation.**</span></span> <span data-ttu-id="514ef-144">Las clases están orientadas a objetos, pero los módulos no lo son.</span><span class="sxs-lookup"><span data-stu-id="514ef-144">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="514ef-145">De modo que solo se pueden crear instancias de las clases como objetos.</span><span class="sxs-lookup"><span data-stu-id="514ef-145">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="514ef-146">Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-146">For more information, see [Objects and Classes](../../programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="514ef-147">Reglas</span><span class="sxs-lookup"><span data-stu-id="514ef-147">Rules</span></span>

- <span data-ttu-id="514ef-148">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="514ef-148">**Modifiers.**</span></span> <span data-ttu-id="514ef-149">Todos los miembros de módulo están [compartidos](../modifiers/shared.md)implícitamente.</span><span class="sxs-lookup"><span data-stu-id="514ef-149">All module members are implicitly [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="514ef-150">No se puede usar la `Shared` palabra clave al declarar un miembro y no se puede modificar el estado compartido de ningún miembro.</span><span class="sxs-lookup"><span data-stu-id="514ef-150">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="514ef-151">**Ella.**</span><span class="sxs-lookup"><span data-stu-id="514ef-151">**Inheritance.**</span></span> <span data-ttu-id="514ef-152">Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object> , del que heredan todos los módulos.</span><span class="sxs-lookup"><span data-stu-id="514ef-152">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="514ef-153">En concreto, un módulo no puede heredar de otro.</span><span class="sxs-lookup"><span data-stu-id="514ef-153">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="514ef-154">No se puede usar la [instrucción Inherits](inherits-statement.md) en una definición de módulo, ni siquiera para especificar <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="514ef-154">You cannot use the [Inherits Statement](inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="514ef-155">**Propiedad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="514ef-155">**Default Property.**</span></span> <span data-ttu-id="514ef-156">No se puede definir ninguna propiedad predeterminada en un módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-156">You cannot define any default properties in a module.</span></span> <span data-ttu-id="514ef-157">Para obtener más información, vea [default](../modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-157">For more information, see [Default](../modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="514ef-158">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="514ef-158">Behavior</span></span>

- <span data-ttu-id="514ef-159">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="514ef-159">**Access Level.**</span></span> <span data-ttu-id="514ef-160">Dentro de un módulo, puede declarar cada miembro con su propio nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="514ef-160">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="514ef-161">Los miembros del módulo tienen acceso [público](../modifiers/public.md) de forma predeterminada, excepto las variables y constantes, que tienen como valor predeterminado el acceso [privado](../modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="514ef-161">Module members default to [Public](../modifiers/public.md) access, except variables and constants, which default to [Private](../modifiers/private.md) access.</span></span> <span data-ttu-id="514ef-162">Cuando un módulo tiene más acceso restringido que uno de sus miembros, tiene prioridad el nivel de acceso del módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="514ef-162">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="514ef-163">**Ámbito.**</span><span class="sxs-lookup"><span data-stu-id="514ef-163">**Scope.**</span></span> <span data-ttu-id="514ef-164">Un módulo está en el ámbito A lo largo de su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="514ef-164">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="514ef-165">El ámbito de cada miembro del módulo es todo el módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-165">The scope of every module member is the entire module.</span></span> <span data-ttu-id="514ef-166">Observe que todos los miembros se someten a la *promoción de tipos*, lo que hace que su ámbito se promueva al espacio de nombres que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-166">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="514ef-167">Para obtener más información, consulte [promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-167">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="514ef-168">**Evaluación.**</span><span class="sxs-lookup"><span data-stu-id="514ef-168">**Qualification.**</span></span> <span data-ttu-id="514ef-169">Puede tener varios módulos en un proyecto y puede declarar miembros con el mismo nombre en dos o más módulos.</span><span class="sxs-lookup"><span data-stu-id="514ef-169">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="514ef-170">Sin embargo, debe calificar cualquier referencia a este miembro con el nombre de módulo adecuado si la referencia es de fuera de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="514ef-170">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="514ef-171">Para obtener más información, consulta [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="514ef-171">For more information, see [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="514ef-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="514ef-172">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="514ef-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="514ef-173">See also</span></span>

- [<span data-ttu-id="514ef-174">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="514ef-174">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="514ef-175">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="514ef-175">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="514ef-176">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="514ef-176">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="514ef-177">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="514ef-177">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="514ef-178">Property Statement</span><span class="sxs-lookup"><span data-stu-id="514ef-178">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="514ef-179">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="514ef-179">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
