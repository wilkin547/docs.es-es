---
title: Tipo de datos definido por el usuario (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 1dac93145b6e11a0d149f03b43e1e0b28b770925
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003181"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="3b83d-102">Tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="3b83d-102">User-Defined Data Type</span></span>
<span data-ttu-id="3b83d-103">Contiene los datos en un formato que defina.</span><span class="sxs-lookup"><span data-stu-id="3b83d-103">Holds data in a format you define.</span></span> <span data-ttu-id="3b83d-104">El `Structure` instrucción define el formato.</span><span class="sxs-lookup"><span data-stu-id="3b83d-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="3b83d-105">Las versiones anteriores de Visual Basic admiten el tipo definido por el usuario (UDT).</span><span class="sxs-lookup"><span data-stu-id="3b83d-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="3b83d-106">La versión actual expande el UDT un *estructura*.</span><span class="sxs-lookup"><span data-stu-id="3b83d-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="3b83d-107">Una estructura es una concatenación de uno o varios *miembros* de diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="3b83d-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="3b83d-108">Visual Basic trata una estructura como una sola unidad, aunque también puede tener acceso a sus miembros individualmente.</span><span class="sxs-lookup"><span data-stu-id="3b83d-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b83d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b83d-109">Remarks</span></span>  
 <span data-ttu-id="3b83d-110">Definir y usar un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una sola unidad, o cuando ninguno de los tipos de datos elementales atender sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="3b83d-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="3b83d-111">El valor predeterminado de un tipo de datos de estructura se compone de la combinación de los valores predeterminados de cada uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="3b83d-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="3b83d-112">Formato de declaración</span><span class="sxs-lookup"><span data-stu-id="3b83d-112">Declaration Format</span></span>  
 <span data-ttu-id="3b83d-113">Una declaración structure comienza con la [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md) y termina con la `End Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3b83d-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="3b83d-114">El `Structure` instrucción proporciona el nombre de la estructura, que también es el identificador del tipo de datos consiste en definir la estructura.</span><span class="sxs-lookup"><span data-stu-id="3b83d-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="3b83d-115">Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y función devuelven valores para que sea del tipo de datos de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="3b83d-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="3b83d-116">Las declaraciones de entre el `Structure` y `End Structure` instrucciones definen los miembros de la estructura.</span><span class="sxs-lookup"><span data-stu-id="3b83d-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="3b83d-117">Niveles de acceso de miembro</span><span class="sxs-lookup"><span data-stu-id="3b83d-117">Member Access Levels</span></span>  
 <span data-ttu-id="3b83d-118">Debe declarar cada miembro utilizando un [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md) o una instrucción que especifica el nivel de acceso, tales como [pública](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="3b83d-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="3b83d-119">Si usa un `Dim` instrucción, los valores predeterminados nivel de acceso público.</span><span class="sxs-lookup"><span data-stu-id="3b83d-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="3b83d-120">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="3b83d-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="3b83d-121">**Consumo de memoria.**</span><span class="sxs-lookup"><span data-stu-id="3b83d-121">**Memory Consumption.**</span></span> <span data-ttu-id="3b83d-122">Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="3b83d-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="3b83d-123">Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración.</span><span class="sxs-lookup"><span data-stu-id="3b83d-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="3b83d-124">Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.</span><span class="sxs-lookup"><span data-stu-id="3b83d-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="3b83d-125">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="3b83d-125">**Interop Considerations.**</span></span> <span data-ttu-id="3b83d-126">Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos definidos por el usuario en otros entornos no son compatibles con Visual Basic los tipos de estructuras.</span><span class="sxs-lookup"><span data-stu-id="3b83d-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="3b83d-127">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="3b83d-127">**Widening.**</span></span> <span data-ttu-id="3b83d-128">No hay ninguna conversión automática a o desde cualquier tipo de datos de estructura.</span><span class="sxs-lookup"><span data-stu-id="3b83d-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="3b83d-129">Puede definir operadores de conversión en la estructura utilizando el [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md), y se puede declarar cada operador de conversión se `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="3b83d-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="3b83d-130">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="3b83d-130">**Type Characters.**</span></span> <span data-ttu-id="3b83d-131">Tipos de datos de estructura no tienen ningún carácter de tipo literal o un carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="3b83d-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="3b83d-132">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="3b83d-132">**Framework Type.**</span></span> <span data-ttu-id="3b83d-133">No hay ningún tipo correspondiente en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b83d-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="3b83d-134">Todas las estructuras heredan de la clase de .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, pero ninguna estructura individual que corresponde a <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3b83d-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b83d-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b83d-135">Example</span></span>  
 <span data-ttu-id="3b83d-136">El paradigma siguiente muestra el esquema de la declaración de una estructura.</span><span class="sxs-lookup"><span data-stu-id="3b83d-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b83d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b83d-137">See Also</span></span>  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [<span data-ttu-id="3b83d-138">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3b83d-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="3b83d-139">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="3b83d-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="3b83d-140">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="3b83d-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="3b83d-141">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3b83d-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="3b83d-142">Widening</span><span class="sxs-lookup"><span data-stu-id="3b83d-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="3b83d-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="3b83d-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="3b83d-144">Estructuras</span><span class="sxs-lookup"><span data-stu-id="3b83d-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="3b83d-145">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3b83d-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
