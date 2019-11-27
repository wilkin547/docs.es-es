---
title: Enum (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 48220fd1e88cf38e67db5dd3a2ad90638eb6b6df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343713"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="477b7-102">Instrucción Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="477b7-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="477b7-103">Declara una enumeración y define los valores de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="477b7-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="477b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="477b7-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="477b7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="477b7-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="477b7-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="477b7-106">Optional.</span></span> <span data-ttu-id="477b7-107">Lista de atributos que se aplican a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="477b7-108">Debe incluir la [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares ("`<`" y "`>`").</span><span class="sxs-lookup"><span data-stu-id="477b7-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="477b7-109">El atributo <xref:System.FlagsAttribute> indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración y que cada miembro representa un campo de bits en el valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="477b7-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="477b7-110">Optional.</span></span> <span data-ttu-id="477b7-111">Especifica qué código puede tener acceso a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="477b7-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="477b7-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="477b7-113">Public</span><span class="sxs-lookup"><span data-stu-id="477b7-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="477b7-114">Protected</span><span class="sxs-lookup"><span data-stu-id="477b7-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="477b7-115">Friend</span><span class="sxs-lookup"><span data-stu-id="477b7-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="477b7-116">Private</span><span class="sxs-lookup"><span data-stu-id="477b7-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="477b7-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="477b7-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="477b7-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="477b7-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="477b7-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="477b7-119">Optional.</span></span> <span data-ttu-id="477b7-120">Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="477b7-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="477b7-121">Solo puede especificar [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) en la propia enumeración, no en ninguno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="477b7-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="477b7-122">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="477b7-122">Required.</span></span> <span data-ttu-id="477b7-123">Nombre de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-123">Name of the enumeration.</span></span> <span data-ttu-id="477b7-124">Para obtener información sobre los nombres válidos, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="477b7-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="477b7-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="477b7-125">Optional.</span></span> <span data-ttu-id="477b7-126">Tipo de datos de la enumeración y de todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="477b7-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="477b7-127">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="477b7-127">Required.</span></span> <span data-ttu-id="477b7-128">Lista de constantes de miembro que se declaran en esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="477b7-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="477b7-129">Aparecen varios miembros en líneas de código fuente individuales.</span><span class="sxs-lookup"><span data-stu-id="477b7-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="477b7-130">Cada `member` tiene la sintaxis y las partes siguientes: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="477b7-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="477b7-131">Parte</span><span class="sxs-lookup"><span data-stu-id="477b7-131">Part</span></span>|<span data-ttu-id="477b7-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="477b7-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="477b7-133">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="477b7-133">Required.</span></span> <span data-ttu-id="477b7-134">Nombre de este miembro.</span><span class="sxs-lookup"><span data-stu-id="477b7-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="477b7-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="477b7-135">Optional.</span></span> <span data-ttu-id="477b7-136">Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.</span><span class="sxs-lookup"><span data-stu-id="477b7-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="477b7-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="477b7-137">`End` `Enum`</span></span>

  <span data-ttu-id="477b7-138">Finaliza el bloque `Enum`.</span><span class="sxs-lookup"><span data-stu-id="477b7-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="477b7-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="477b7-139">Remarks</span></span>

<span data-ttu-id="477b7-140">Si tiene un conjunto de valores invariables que están relacionados lógicamente entre sí, puede definirlos juntos en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="477b7-141">Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores.</span><span class="sxs-lookup"><span data-stu-id="477b7-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="477b7-142">Después, puede usar los miembros de enumeración en muchos lugares del código.</span><span class="sxs-lookup"><span data-stu-id="477b7-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="477b7-143">Las ventajas de utilizar enumeraciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="477b7-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="477b7-144">Reduce los errores causados por la transposición o la escritura indebida de números.</span><span class="sxs-lookup"><span data-stu-id="477b7-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="477b7-145">Facilita el cambio de valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="477b7-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="477b7-146">Facilita la lectura del código, lo que significa que es menos probable que se introduzcan errores.</span><span class="sxs-lookup"><span data-stu-id="477b7-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="477b7-147">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="477b7-147">Ensures forward compatibility.</span></span> <span data-ttu-id="477b7-148">Si usa enumeraciones, es menos probable que se produzca un error en el código si en el futuro alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="477b7-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="477b7-149">Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros.</span><span class="sxs-lookup"><span data-stu-id="477b7-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="477b7-150">Cada miembro representa una constante.</span><span class="sxs-lookup"><span data-stu-id="477b7-150">Each member represents a constant.</span></span>

<span data-ttu-id="477b7-151">Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es una *enumeración de miembros*.</span><span class="sxs-lookup"><span data-stu-id="477b7-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="477b7-152">Es miembro de la clase, estructura, módulo o interfaz que lo declara.</span><span class="sxs-lookup"><span data-stu-id="477b7-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="477b7-153">Se puede tener acceso a las enumeraciones de miembros desde cualquier lugar dentro de su clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="477b7-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="477b7-154">El código fuera de una clase, estructura o módulo debe calificar el nombre de la enumeración de un miembro con el nombre de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="477b7-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="477b7-155">Puede evitar la necesidad de usar nombres completos agregando una instrucción [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) al archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="477b7-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="477b7-156">Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="477b7-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="477b7-157">El *contexto* de la declaración de una enumeración debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="477b7-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="477b7-158">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="477b7-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="477b7-159">Puede aplicar atributos a una enumeración en su totalidad, pero no a sus miembros individualmente.</span><span class="sxs-lookup"><span data-stu-id="477b7-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="477b7-160">Un atributo contribuye a la información en los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="477b7-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="477b7-161">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="477b7-161">Data Type</span></span>

<span data-ttu-id="477b7-162">La instrucción `Enum` puede declarar el tipo de datos de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="477b7-163">Cada miembro toma el tipo de datos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="477b7-164">Puede especificar `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`o `UShort`.</span><span class="sxs-lookup"><span data-stu-id="477b7-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="477b7-165">Si no especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer`.</span><span class="sxs-lookup"><span data-stu-id="477b7-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="477b7-166">Si especifica `datatype` y `initializer`, el tipo de datos de `initializer` debe ser convertible en `datatype`.</span><span class="sxs-lookup"><span data-stu-id="477b7-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="477b7-167">Si no hay ningún `datatype` ni `initializer`, el tipo de datos tiene como valor predeterminado `Integer`.</span><span class="sxs-lookup"><span data-stu-id="477b7-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="477b7-168">Inicializar miembros</span><span class="sxs-lookup"><span data-stu-id="477b7-168">Initializing Members</span></span>

<span data-ttu-id="477b7-169">La instrucción `Enum` puede inicializar el contenido de los miembros seleccionados en `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="477b7-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="477b7-170">Utilice `initializer` para proporcionar una expresión que se va a asignar al miembro.</span><span class="sxs-lookup"><span data-stu-id="477b7-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="477b7-171">Si no especifica `initializer` para un miembro, Visual Basic lo inicializa en cero (si es el primer `member` de `memberlist`) o en un valor mayor en uno que el de la `member`inmediatamente anterior.</span><span class="sxs-lookup"><span data-stu-id="477b7-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="477b7-172">La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos, incluido un miembro anterior de esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="477b7-173">Puede usar operadores aritméticos y lógicos para combinar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="477b7-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="477b7-174">No se pueden usar variables ni funciones en `initializer`.</span><span class="sxs-lookup"><span data-stu-id="477b7-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="477b7-175">Sin embargo, puede usar palabras clave de conversión como `CByte` y `CShort`.</span><span class="sxs-lookup"><span data-stu-id="477b7-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="477b7-176">También puede utilizar `AscW` si lo llama con una constante `String` o `Char` argumento, ya que se puede evaluar en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="477b7-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="477b7-177">Las enumeraciones no pueden tener valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="477b7-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="477b7-178">Si a un miembro se le asigna un valor de punto flotante y `Option Strict` está establecido en ON, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="477b7-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="477b7-179">Si `Option Strict` está desactivado, el valor se convierte automáticamente al tipo de `Enum`.</span><span class="sxs-lookup"><span data-stu-id="477b7-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="477b7-180">Si el valor de un miembro supera el intervalo permitido para el tipo de datos subyacente, o si se inicializa un miembro con el valor máximo permitido por el tipo de datos subyacente, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="477b7-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="477b7-181">Modificadores</span><span class="sxs-lookup"><span data-stu-id="477b7-181">Modifiers</span></span>

<span data-ttu-id="477b7-182">Las enumeraciones de clase, estructura, módulo y miembro de interfaz tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="477b7-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="477b7-183">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="477b7-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="477b7-184">Las enumeraciones de miembros de espacio de nombres tienen acceso de confianza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="477b7-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="477b7-185">Puede ajustar sus niveles de acceso a público, pero no a privado o protegido.</span><span class="sxs-lookup"><span data-stu-id="477b7-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="477b7-186">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="477b7-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="477b7-187">Todos los miembros de enumeración tienen acceso público y no se pueden usar modificadores de acceso en ellos.</span><span class="sxs-lookup"><span data-stu-id="477b7-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="477b7-188">Sin embargo, si la propia enumeración tiene un nivel de acceso más restringido, tiene prioridad el nivel de acceso de enumeración especificado.</span><span class="sxs-lookup"><span data-stu-id="477b7-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="477b7-189">De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes.</span><span class="sxs-lookup"><span data-stu-id="477b7-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="477b7-190">Por lo tanto, las palabras clave `Shared`, `Static`y `ReadOnly` no se pueden usar al declarar una enumeración o sus miembros.</span><span class="sxs-lookup"><span data-stu-id="477b7-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="477b7-191">Asignar varios valores</span><span class="sxs-lookup"><span data-stu-id="477b7-191">Assigning Multiple Values</span></span>

<span data-ttu-id="477b7-192">Las enumeraciones suelen representar valores mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="477b7-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="477b7-193">Al incluir el atributo <xref:System.FlagsAttribute> en la declaración de `Enum`, en su lugar puede asignar varios valores a una instancia de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="477b7-194">El atributo <xref:System.FlagsAttribute> especifica que la enumeración se tratará como un campo de bits, es decir, un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="477b7-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="477b7-195">Se denominan enumeraciones *bit a bit* .</span><span class="sxs-lookup"><span data-stu-id="477b7-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="477b7-196">Cuando se declara una enumeración mediante el atributo <xref:System.FlagsAttribute>, se recomienda usar las potencias de 2, es decir, 1, 2, 4, 8, 16, etc., para los valores.</span><span class="sxs-lookup"><span data-stu-id="477b7-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="477b7-197">También se recomienda que "none" sea el nombre de un miembro cuyo valor sea 0.</span><span class="sxs-lookup"><span data-stu-id="477b7-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="477b7-198">Para obtener instrucciones adicionales, vea <xref:System.FlagsAttribute> y <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="477b7-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="477b7-199">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-199">Example</span></span>

<span data-ttu-id="477b7-200">En el ejemplo siguiente se muestra cómo usar la instrucción `Enum`.</span><span class="sxs-lookup"><span data-stu-id="477b7-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="477b7-201">Tenga en cuenta que el miembro se conoce como `EggSizeEnum.Medium`y no como `Medium`.</span><span class="sxs-lookup"><span data-stu-id="477b7-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="477b7-202">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-202">Example</span></span>

<span data-ttu-id="477b7-203">El método del ejemplo siguiente está fuera de la clase `Egg`.</span><span class="sxs-lookup"><span data-stu-id="477b7-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="477b7-204">Por lo tanto, `EggSizeEnum` se califica como `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="477b7-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="477b7-205">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-205">Example</span></span>

<span data-ttu-id="477b7-206">En el ejemplo siguiente se usa la instrucción `Enum` para definir un conjunto relacionado de valores constantes con nombre.</span><span class="sxs-lookup"><span data-stu-id="477b7-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="477b7-207">En este caso, los valores son colores que se pueden elegir para diseñar formularios de entrada de datos para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="477b7-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="477b7-208">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-208">Example</span></span>

<span data-ttu-id="477b7-209">En el ejemplo siguiente se muestran valores que incluyen números positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="477b7-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="477b7-210">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-210">Example</span></span>

<span data-ttu-id="477b7-211">En el ejemplo siguiente, se utiliza una cláusula `As` para especificar el `datatype` de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="477b7-212">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-212">Example</span></span>

<span data-ttu-id="477b7-213">En el ejemplo siguiente se muestra cómo usar una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="477b7-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="477b7-214">Se pueden asignar varios valores a una instancia de una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="477b7-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="477b7-215">La declaración de `Enum` incluye el atributo <xref:System.FlagsAttribute>, que indica que la enumeración se puede tratar como un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="477b7-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="477b7-216">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="477b7-216">Example</span></span>

<span data-ttu-id="477b7-217">En el ejemplo siguiente se recorre en iteración una enumeración.</span><span class="sxs-lookup"><span data-stu-id="477b7-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="477b7-218">Usa el método <xref:System.Enum.GetNames%2A> para recuperar una matriz de nombres de miembro de la enumeración y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.</span><span class="sxs-lookup"><span data-stu-id="477b7-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="477b7-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="477b7-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="477b7-220">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="477b7-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="477b7-221">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="477b7-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="477b7-222">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="477b7-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="477b7-223">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="477b7-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="477b7-224">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="477b7-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
