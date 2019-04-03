---
title: Instrucción Enum (Visual Basic)
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
ms.openlocfilehash: fa97a374d4570e014222bf44844271b3394453da
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830076"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="cf689-102">Instrucción Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf689-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="cf689-103">Declara una enumeración y define los valores de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf689-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf689-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf689-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="cf689-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="cf689-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="cf689-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf689-106">Optional.</span></span> <span data-ttu-id="cf689-107">Lista de atributos que se aplican a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="cf689-108">Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").</span><span class="sxs-lookup"><span data-stu-id="cf689-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="cf689-109">El <xref:System.FlagsAttribute> atributo indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración, y que cada miembro representa un campo de bits en el valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="cf689-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf689-110">Optional.</span></span> <span data-ttu-id="cf689-111">Especifica qué código puede tener acceso a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="cf689-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf689-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="cf689-113">Public</span><span class="sxs-lookup"><span data-stu-id="cf689-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="cf689-114">Protected</span><span class="sxs-lookup"><span data-stu-id="cf689-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="cf689-115">Friend</span><span class="sxs-lookup"><span data-stu-id="cf689-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="cf689-116">Private</span><span class="sxs-lookup"><span data-stu-id="cf689-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="cf689-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="cf689-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="cf689-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="cf689-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

-   `Shadows`  
  
     <span data-ttu-id="cf689-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf689-119">Optional.</span></span> <span data-ttu-id="cf689-120">Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación con el mismo nombre o el conjunto de elementos sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="cf689-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="cf689-121">Puede especificar [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) solo en la propia enumeración, no en cualquiera de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf689-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="cf689-122">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cf689-122">Required.</span></span> <span data-ttu-id="cf689-123">Nombre de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-123">Name of the enumeration.</span></span> <span data-ttu-id="cf689-124">Para obtener información sobre los nombres válidos, vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="cf689-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="cf689-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf689-125">Optional.</span></span> <span data-ttu-id="cf689-126">Tipo de datos de la enumeración y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf689-126">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="cf689-127">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cf689-127">Required.</span></span> <span data-ttu-id="cf689-128">Lista de constantes de miembros que se declaran en esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="cf689-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="cf689-129">Varios miembros aparecen en líneas de código fuente individuales.</span><span class="sxs-lookup"><span data-stu-id="cf689-129">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="cf689-130">Cada `member` tiene la sintaxis y las partes siguientes: `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="cf689-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="cf689-131">Parte</span><span class="sxs-lookup"><span data-stu-id="cf689-131">Part</span></span>|<span data-ttu-id="cf689-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf689-132">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="cf689-133">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cf689-133">Required.</span></span> <span data-ttu-id="cf689-134">Nombre de este miembro.</span><span class="sxs-lookup"><span data-stu-id="cf689-134">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="cf689-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf689-135">Optional.</span></span> <span data-ttu-id="cf689-136">Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.</span><span class="sxs-lookup"><span data-stu-id="cf689-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="cf689-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="cf689-137">`End` `Enum`</span></span>  
  
     <span data-ttu-id="cf689-138">Finaliza el bloque `Enum`.</span><span class="sxs-lookup"><span data-stu-id="cf689-138">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf689-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf689-139">Remarks</span></span>  
 <span data-ttu-id="cf689-140">Si tiene un conjunto de valores inmutables que se relacionan lógicamente entre sí, puede definirlos juntos en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="cf689-141">Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores.</span><span class="sxs-lookup"><span data-stu-id="cf689-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="cf689-142">A continuación, puede utilizar a los miembros de enumeración en muchos lugares del código.</span><span class="sxs-lookup"><span data-stu-id="cf689-142">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="cf689-143">Las ventajas de usar las enumeraciones incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf689-143">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="cf689-144">Reduce los errores causados por números transpuestos o.</span><span class="sxs-lookup"><span data-stu-id="cf689-144">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="cf689-145">Es fácil cambiar los valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="cf689-145">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="cf689-146">Hace el código más fácil de leer, lo que significa que es menos probable que se van a introducir errores.</span><span class="sxs-lookup"><span data-stu-id="cf689-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="cf689-147">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cf689-147">Ensures forward compatibility.</span></span> <span data-ttu-id="cf689-148">Si utiliza las enumeraciones, el código es menos propenso a errores si en el futuro que alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="cf689-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="cf689-149">Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros.</span><span class="sxs-lookup"><span data-stu-id="cf689-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="cf689-150">Cada miembro representa una constante.</span><span class="sxs-lookup"><span data-stu-id="cf689-150">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="cf689-151">Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es un *enumeración de miembros*.</span><span class="sxs-lookup"><span data-stu-id="cf689-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="cf689-152">Es un miembro de la clase, estructura, módulo o interfaz que la declara.</span><span class="sxs-lookup"><span data-stu-id="cf689-152">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="cf689-153">Las enumeraciones de miembros se pueden acceder desde cualquier lugar dentro de su clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="cf689-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="cf689-154">Código fuera de una clase, estructura o módulo debe calificar el nombre de una enumeración de miembros con el nombre de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="cf689-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="cf689-155">Puede evitar la necesidad de utilizar nombres completos mediante la adición de un [importaciones](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) instrucción al archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="cf689-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="cf689-156">Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="cf689-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="cf689-157">El *contexto de declaración* para una enumeración debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="cf689-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="cf689-158">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="cf689-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="cf689-159">Se puede aplicar los atributos a una enumeración como un todo, pero no a sus miembros individualmente.</span><span class="sxs-lookup"><span data-stu-id="cf689-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="cf689-160">Un atributo proporciona información a los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cf689-160">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="cf689-161">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cf689-161">Data Type</span></span>  
 <span data-ttu-id="cf689-162">El `Enum` instrucción puede declarar el tipo de datos de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="cf689-163">Cada miembro toma el tipo de datos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="cf689-164">Puede especificar `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.</span><span class="sxs-lookup"><span data-stu-id="cf689-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="cf689-165">Si no especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer`.</span><span class="sxs-lookup"><span data-stu-id="cf689-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="cf689-166">Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe ser convertible a `datatype`.</span><span class="sxs-lookup"><span data-stu-id="cf689-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="cf689-167">Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Integer`.</span><span class="sxs-lookup"><span data-stu-id="cf689-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="cf689-168">Inicialización de miembros</span><span class="sxs-lookup"><span data-stu-id="cf689-168">Initializing Members</span></span>  
 <span data-ttu-id="cf689-169">El `Enum` instrucción puede inicializar el contenido de los miembros seleccionados en `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="cf689-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="cf689-170">Usa `initializer` para proporcionar una expresión que se asigna al miembro.</span><span class="sxs-lookup"><span data-stu-id="cf689-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="cf689-171">Si no especifica `initializer` para un miembro, Visual Basic la inicializa a cero (si es la primera `member` en `memberlist`), o en un valor mayor en uno que el de la inmediatamente anterior `member`.</span><span class="sxs-lookup"><span data-stu-id="cf689-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="cf689-172">La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos, incluso un miembro anterior de esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="cf689-173">Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="cf689-173">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="cf689-174">No se puede usar las variables o funciones en `initializer`.</span><span class="sxs-lookup"><span data-stu-id="cf689-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="cf689-175">Sin embargo, puede usar palabras clave de conversión, como `CByte` y `CShort`.</span><span class="sxs-lookup"><span data-stu-id="cf689-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="cf689-176">También puede usar `AscW` si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="cf689-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="cf689-177">Las enumeraciones no pueden tener valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="cf689-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="cf689-178">Si un miembro se le asigna un valor de punto flotante y `Option Strict` se establece en on, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="cf689-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="cf689-179">Si `Option Strict` está desactivado, el valor se convierte automáticamente en el `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="cf689-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="cf689-180">Si el valor de un miembro supera el intervalo permitido para el tipo de datos subyacente, o si se inicializa a un miembro al valor máximo permitido por el tipo de datos subyacente, el compilador notifica un error.</span><span class="sxs-lookup"><span data-stu-id="cf689-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="cf689-181">Modificadores</span><span class="sxs-lookup"><span data-stu-id="cf689-181">Modifiers</span></span>  
 <span data-ttu-id="cf689-182">Clase, estructura, módulo y predeterminado de enumeraciones de miembro de interfaz para acceso público.</span><span class="sxs-lookup"><span data-stu-id="cf689-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="cf689-183">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="cf689-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="cf689-184">Namespace predeterminado de enumeraciones de miembro para el acceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="cf689-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="cf689-185">Puede ajustar sus niveles de acceso público, pero no a privado o protegido.</span><span class="sxs-lookup"><span data-stu-id="cf689-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="cf689-186">Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cf689-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="cf689-187">Todos los miembros de enumeración tienen acceso público y no se puede usar cualquier modificador de acceso en ellos.</span><span class="sxs-lookup"><span data-stu-id="cf689-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="cf689-188">Sin embargo, si la propia enumeración tiene un nivel de acceso más restrictivos, el nivel de acceso de la enumeración especificada tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="cf689-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="cf689-189">De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes.</span><span class="sxs-lookup"><span data-stu-id="cf689-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="cf689-190">Por lo tanto, el `Shared`, `Static`, y `ReadOnly` palabras clave no se puede usar cuando se declara una enumeración o sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf689-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="cf689-191">Asignación de varios valores</span><span class="sxs-lookup"><span data-stu-id="cf689-191">Assigning Multiple Values</span></span>  
 <span data-ttu-id="cf689-192">Enumeraciones suelen representan valores mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="cf689-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="cf689-193">Al incluir el <xref:System.FlagsAttribute> atributo el `Enum` declaración, en su lugar, puede asignar varios valores a una instancia de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="cf689-194">El <xref:System.FlagsAttribute> atributo especifica que la enumeración se tratan como un campo de bits, es decir, un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="cf689-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="cf689-195">Se denominan *bit a bit* enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="cf689-195">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="cf689-196">Al declarar una enumeración mediante el uso de la <xref:System.FlagsAttribute> atributo, se recomienda que use potencias de 2, que es, 1, 2, 4, 8, 16 y así sucesivamente, para los valores.</span><span class="sxs-lookup"><span data-stu-id="cf689-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="cf689-197">También se recomienda que "" ser el nombre de un miembro cuyo valor es 0.</span><span class="sxs-lookup"><span data-stu-id="cf689-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="cf689-198">Para obtener instrucciones adicionales, consulte <xref:System.FlagsAttribute> y <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="cf689-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf689-199">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-199">Example</span></span>  
 <span data-ttu-id="cf689-200">En el ejemplo siguiente se muestra cómo usar la instrucción `Enum`.</span><span class="sxs-lookup"><span data-stu-id="cf689-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="cf689-201">Tenga en cuenta que el miembro se conoce como `EggSizeEnum.Medium`y no como `Medium`.</span><span class="sxs-lookup"><span data-stu-id="cf689-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="cf689-202">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-202">Example</span></span>  
 <span data-ttu-id="cf689-203">El método en el ejemplo siguiente está fuera del `Egg` clase.</span><span class="sxs-lookup"><span data-stu-id="cf689-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="cf689-204">Por lo tanto, `EggSizeEnum` es un nombre completo como `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="cf689-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="cf689-205">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-205">Example</span></span>  
 <span data-ttu-id="cf689-206">En el ejemplo siguiente se usa el `Enum` denominado de instrucción para definir un conjunto relacionado de valores constantes.</span><span class="sxs-lookup"><span data-stu-id="cf689-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="cf689-207">En este caso, los valores son colores que puede optar por diseñar formularios de entrada de datos para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="cf689-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="cf689-208">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-208">Example</span></span>  
 <span data-ttu-id="cf689-209">El ejemplo siguiente muestra los valores que incluyen números positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="cf689-209">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="cf689-210">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-210">Example</span></span>  
 <span data-ttu-id="cf689-211">En el ejemplo siguiente, un `As` cláusula se utiliza para especificar el `datatype` de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="cf689-212">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-212">Example</span></span>  
 <span data-ttu-id="cf689-213">El ejemplo siguiente muestra cómo utilizar una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cf689-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="cf689-214">Varios valores se pueden asignar a una instancia de una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cf689-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="cf689-215">El `Enum` declaración incluye el <xref:System.FlagsAttribute> atributo, que indica que la enumeración se puede tratar como un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="cf689-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="cf689-216">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf689-216">Example</span></span>  
 <span data-ttu-id="cf689-217">El ejemplo siguiente se recorre en iteración una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cf689-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="cf689-218">Usa el <xref:System.Enum.GetNames%2A> método para recuperar una matriz de nombres de miembro de la enumeración, y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.</span><span class="sxs-lookup"><span data-stu-id="cf689-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]  
  
## <a name="see-also"></a><span data-ttu-id="cf689-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf689-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="cf689-220">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cf689-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="cf689-221">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cf689-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="cf689-222">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="cf689-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="cf689-223">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="cf689-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cf689-224">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="cf689-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
