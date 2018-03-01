---
title: "Instrucción Enum (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a8244318e0be8e50f3384b56cf63e59182b6cda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="61f9e-102">Instrucción Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f9e-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="61f9e-103">Declara una enumeración y define los valores de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="61f9e-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f9e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61f9e-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="61f9e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="61f9e-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="61f9e-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="61f9e-106">Optional.</span></span> <span data-ttu-id="61f9e-107">Lista de atributos que se aplican a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="61f9e-108">Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) corchetes angulares ("`<`"y"`>`").</span><span class="sxs-lookup"><span data-stu-id="61f9e-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="61f9e-109">El <xref:System.FlagsAttribute> atributo indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración y que cada miembro representa un campo de bits en el valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="61f9e-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="61f9e-110">Optional.</span></span> <span data-ttu-id="61f9e-111">Especifica qué código puede tener acceso a esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="61f9e-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="61f9e-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="61f9e-113">Public</span><span class="sxs-lookup"><span data-stu-id="61f9e-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="61f9e-114">Protected</span><span class="sxs-lookup"><span data-stu-id="61f9e-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="61f9e-115">Friend</span><span class="sxs-lookup"><span data-stu-id="61f9e-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="61f9e-116">Private</span><span class="sxs-lookup"><span data-stu-id="61f9e-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="61f9e-117">Puede especificar `Protected``Friend` para permitir el acceso desde el código dentro de la clase de la enumeración, una clase derivada o el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="61f9e-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="61f9e-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="61f9e-118">Optional.</span></span> <span data-ttu-id="61f9e-119">Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación denominado de forma idéntica, o un conjunto de elementos sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="61f9e-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="61f9e-120">Puede especificar [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) solo en la propia enumeración, no en cualquiera de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="61f9e-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="61f9e-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="61f9e-121">Required.</span></span> <span data-ttu-id="61f9e-122">Nombre de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-122">Name of the enumeration.</span></span> <span data-ttu-id="61f9e-123">Para obtener información sobre los nombres válidos, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="61f9e-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="61f9e-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="61f9e-124">Optional.</span></span> <span data-ttu-id="61f9e-125">Tipo de datos de la enumeración y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="61f9e-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="61f9e-126">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="61f9e-126">Required.</span></span> <span data-ttu-id="61f9e-127">Lista de constantes de miembros que se declaran en esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="61f9e-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="61f9e-128">Varios miembros aparecen en las líneas de código fuente individual.</span><span class="sxs-lookup"><span data-stu-id="61f9e-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="61f9e-129">Cada `member` tiene la sintaxis y las partes siguientes:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="61f9e-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="61f9e-130">Parte</span><span class="sxs-lookup"><span data-stu-id="61f9e-130">Part</span></span>|<span data-ttu-id="61f9e-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="61f9e-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="61f9e-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="61f9e-132">Required.</span></span> <span data-ttu-id="61f9e-133">Nombre de este miembro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="61f9e-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="61f9e-134">Optional.</span></span> <span data-ttu-id="61f9e-135">Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="61f9e-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="61f9e-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="61f9e-137">Finaliza el bloque `Enum`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61f9e-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="61f9e-138">Remarks</span></span>  
 <span data-ttu-id="61f9e-139">Si tiene un conjunto de valores inalterables que se relacionan lógicamente entre sí, puede definirlos juntos en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="61f9e-140">Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores.</span><span class="sxs-lookup"><span data-stu-id="61f9e-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="61f9e-141">A continuación, puede utilizar a los miembros de enumeración en muchos lugares en el código.</span><span class="sxs-lookup"><span data-stu-id="61f9e-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="61f9e-142">Las ventajas de usar las enumeraciones incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="61f9e-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="61f9e-143">Reducir los errores producidos por números transpuestos o.</span><span class="sxs-lookup"><span data-stu-id="61f9e-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="61f9e-144">Resulta muy sencillo cambiar valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="61f9e-145">Obtiene un código más fácil de leer, lo que significa que es menos probable que los errores se introducirán.</span><span class="sxs-lookup"><span data-stu-id="61f9e-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="61f9e-146">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="61f9e-146">Ensures forward compatibility.</span></span> <span data-ttu-id="61f9e-147">Si utiliza las enumeraciones, el código es menos probable que se produzca un error si en el futuro en que alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="61f9e-148">Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros.</span><span class="sxs-lookup"><span data-stu-id="61f9e-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="61f9e-149">Cada miembro representa una constante.</span><span class="sxs-lookup"><span data-stu-id="61f9e-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="61f9e-150">Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es un *enumeración de miembros*.</span><span class="sxs-lookup"><span data-stu-id="61f9e-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="61f9e-151">Es un miembro de la clase, estructura, módulo o interfaz que lo declara.</span><span class="sxs-lookup"><span data-stu-id="61f9e-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="61f9e-152">Las enumeraciones de miembros pueden tener acceso desde cualquier dentro de su clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="61f9e-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="61f9e-153">Código fuera de una clase, estructura o módulo debe calificar el nombre de una enumeración de miembros con el nombre de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="61f9e-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="61f9e-154">Puede evitar la necesidad de utilizar nombres completos, agregue un [importaciones](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) instrucción al archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="61f9e-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="61f9e-155">Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="61f9e-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="61f9e-156">El *contexto de la declaración* para una enumeración debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="61f9e-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="61f9e-157">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="61f9e-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="61f9e-158">Se pueden aplicar los atributos a una enumeración como un todo, pero no a sus miembros individualmente.</span><span class="sxs-lookup"><span data-stu-id="61f9e-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="61f9e-159">Un atributo proporciona información a los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="61f9e-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="61f9e-160">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="61f9e-160">Data Type</span></span>  
 <span data-ttu-id="61f9e-161">El `Enum` instrucción puede declarar el tipo de datos de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="61f9e-162">Cada miembro toma el tipo de datos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="61f9e-163">Puede especificar `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="61f9e-164">Si no se especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="61f9e-165">Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe poder convertirse a `datatype`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="61f9e-166">Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Integer`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="61f9e-167">Inicialización de miembros</span><span class="sxs-lookup"><span data-stu-id="61f9e-167">Initializing Members</span></span>  
 <span data-ttu-id="61f9e-168">El `Enum` instrucción puede inicializar el contenido de los miembros seleccionados en `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="61f9e-169">Utiliza `initializer` para proporcionar una expresión que se asignará al miembro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="61f9e-170">Si no se especifica `initializer` de un miembro, Visual Basic lo inicializa a cero (si es la primera `member` en `memberlist`), o en un valor superior en uno al de la antecede `member`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="61f9e-171">La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya se han definido y miembros de enumeración que ya están definidos, incluso un miembro anterior de esta enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="61f9e-172">Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="61f9e-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="61f9e-173">No se puede utilizar variables o funciones en `initializer`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="61f9e-174">Sin embargo, puede usar palabras clave de conversión como `CByte` y `CShort`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="61f9e-175">También puede usar `AscW` si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="61f9e-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="61f9e-176">Las enumeraciones no pueden tener valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="61f9e-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="61f9e-177">Si un miembro se le asigna un valor de punto flotante y `Option Strict` se establece en on, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="61f9e-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="61f9e-178">Si `Option Strict` está desactivado, el valor se convierte automáticamente en el `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="61f9e-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="61f9e-179">Si el valor de un miembro supera el intervalo permitido para el tipo de datos subyacente, o si se inicializa a un miembro al valor máximo permitido por el tipo de datos subyacente, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="61f9e-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="61f9e-180">Modificadores</span><span class="sxs-lookup"><span data-stu-id="61f9e-180">Modifiers</span></span>  
 <span data-ttu-id="61f9e-181">Clase, estructura, módulo y predeterminada de enumeraciones de miembro de interfaz para acceso público.</span><span class="sxs-lookup"><span data-stu-id="61f9e-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="61f9e-182">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="61f9e-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="61f9e-183">Namespace miembros enumeraciones como valor predeterminado para el acceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="61f9e-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="61f9e-184">Puede ajustar los niveles de acceso público, pero no a privado o protegido.</span><span class="sxs-lookup"><span data-stu-id="61f9e-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="61f9e-185">Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="61f9e-185">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="61f9e-186">Todos los miembros de enumeración tienen acceso público y no puede usar los modificadores de acceso en ellos.</span><span class="sxs-lookup"><span data-stu-id="61f9e-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="61f9e-187">Sin embargo, si la propia enumeración tiene un nivel de acceso más limitado, el nivel de acceso de la enumeración especificada tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="61f9e-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="61f9e-188">De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes.</span><span class="sxs-lookup"><span data-stu-id="61f9e-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="61f9e-189">Por lo tanto, la `Shared`, `Static`, y `ReadOnly` no se puede usar palabras clave al declarar una enumeración o sus miembros.</span><span class="sxs-lookup"><span data-stu-id="61f9e-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="61f9e-190">Asignación de varios valores</span><span class="sxs-lookup"><span data-stu-id="61f9e-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="61f9e-191">Enumeraciones suelen representan valores mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="61f9e-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="61f9e-192">Mediante la inclusión de la <xref:System.FlagsAttribute> de atributo en el `Enum` declaración, en su lugar, puede asignar varios valores a una instancia de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="61f9e-193">El <xref:System.FlagsAttribute> atributo especifica que la enumeración se tratan como un campo de bits, es decir, un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="61f9e-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="61f9e-194">Se denominan *bit a bit* enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="61f9e-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="61f9e-195">Cuando se declara una enumeración mediante el uso de la <xref:System.FlagsAttribute> atributo, recomendamos que use potencias de 2, que es 1, 2, 4, 8, 16 y así sucesivamente, para los valores.</span><span class="sxs-lookup"><span data-stu-id="61f9e-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="61f9e-196">También se recomienda que "" sea el nombre de un miembro cuyo valor es 0.</span><span class="sxs-lookup"><span data-stu-id="61f9e-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="61f9e-197">Para obtener instrucciones adicionales, vea <xref:System.FlagsAttribute> y <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="61f9e-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f9e-198">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-198">Example</span></span>  
 <span data-ttu-id="61f9e-199">En el ejemplo siguiente se muestra cómo utilizar el `Enum` instrucción.</span><span class="sxs-lookup"><span data-stu-id="61f9e-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="61f9e-200">Tenga en cuenta que el miembro se conoce como `EggSizeEnum.Medium`y no como `Medium`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-201">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-201">Example</span></span>  
 <span data-ttu-id="61f9e-202">El método en el ejemplo siguiente está fuera de la `Egg` clase.</span><span class="sxs-lookup"><span data-stu-id="61f9e-202">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="61f9e-203">Por lo tanto, `EggSizeEnum` es un nombre completo como `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="61f9e-203">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-204">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-204">Example</span></span>  
 <span data-ttu-id="61f9e-205">En el ejemplo siguiente se usa el `Enum` denominado de instrucción para definir un conjunto relacionado de valores constantes.</span><span class="sxs-lookup"><span data-stu-id="61f9e-205">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="61f9e-206">En este caso, los valores son colores que puede elegir para diseñar formularios de entrada de datos para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="61f9e-206">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-207">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-207">Example</span></span>  
 <span data-ttu-id="61f9e-208">En el ejemplo siguiente se muestra los valores que incluyen números positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="61f9e-208">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-209">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-209">Example</span></span>  
 <span data-ttu-id="61f9e-210">En el ejemplo siguiente, un `As` cláusula se utiliza para especificar el `datatype` de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-210">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-211">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-211">Example</span></span>  
 <span data-ttu-id="61f9e-212">En el ejemplo siguiente se muestra cómo utilizar una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="61f9e-212">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="61f9e-213">Varios valores pueden asignarse a una instancia de una enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="61f9e-213">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="61f9e-214">El `Enum` declaración incluye la <xref:System.FlagsAttribute> atributo, que indica que la enumeración se puede tratar como un conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="61f9e-214">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="61f9e-215">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f9e-215">Example</span></span>  
 <span data-ttu-id="61f9e-216">En el ejemplo siguiente se recorre en iteración una enumeración.</span><span class="sxs-lookup"><span data-stu-id="61f9e-216">The following example iterates through an enumeration.</span></span> <span data-ttu-id="61f9e-217">Usa el <xref:System.Enum.GetNames%2A> método para recuperar una matriz de nombres de miembro de la enumeración, y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.</span><span class="sxs-lookup"><span data-stu-id="61f9e-217">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="61f9e-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="61f9e-218">See Also</span></span>  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="61f9e-219">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="61f9e-219">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="61f9e-220">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="61f9e-220">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="61f9e-221">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="61f9e-221">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="61f9e-222">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="61f9e-222">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="61f9e-223">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="61f9e-223">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
