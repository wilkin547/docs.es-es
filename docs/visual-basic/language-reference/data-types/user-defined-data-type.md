---
title: Tipo de datos definido por el usuario
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
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415497"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="9f439-102">Tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="9f439-102">User-Defined Data Type</span></span>

<span data-ttu-id="9f439-103">Contiene los datos en un formato definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9f439-103">Holds data in a format you define.</span></span> <span data-ttu-id="9f439-104">La `Structure` instrucción define el formato.</span><span class="sxs-lookup"><span data-stu-id="9f439-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="9f439-105">Las versiones anteriores de Visual Basic admiten el tipo definido por el usuario (UDT).</span><span class="sxs-lookup"><span data-stu-id="9f439-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="9f439-106">La versión actual expande el UDT a una *estructura*.</span><span class="sxs-lookup"><span data-stu-id="9f439-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="9f439-107">Una estructura es una concatenación de uno o más *miembros* de varios tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="9f439-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="9f439-108">Visual Basic trata una estructura como una sola unidad, aunque también puede tener acceso a sus miembros individualmente.</span><span class="sxs-lookup"><span data-stu-id="9f439-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f439-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9f439-109">Remarks</span></span>

<span data-ttu-id="9f439-110">Defina y use un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una sola unidad, o cuando ninguno de los tipos de datos básicos satisfaga sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="9f439-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="9f439-111">El valor predeterminado de un tipo de datos de estructura consta de la combinación de los valores predeterminados de cada uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="9f439-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="9f439-112">Formato de declaración</span><span class="sxs-lookup"><span data-stu-id="9f439-112">Declaration Format</span></span>

<span data-ttu-id="9f439-113">Una declaración de estructura comienza con la [instrucción Structure](../statements/structure-statement.md) y termina con la `End Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9f439-113">A structure declaration starts with the [Structure Statement](../statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="9f439-114">La `Structure` instrucción proporciona el nombre de la estructura, que también es el identificador del tipo de datos que la estructura está definiendo.</span><span class="sxs-lookup"><span data-stu-id="9f439-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="9f439-115">Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y valores devueltos por la función para que sean del tipo de datos de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="9f439-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="9f439-116">Las declaraciones entre las `Structure` instrucciones y `End Structure` definen los miembros de la estructura.</span><span class="sxs-lookup"><span data-stu-id="9f439-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="9f439-117">Niveles de acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="9f439-117">Member Access Levels</span></span>

<span data-ttu-id="9f439-118">Debe declarar cada miembro mediante una [instrucción Dim](../statements/dim-statement.md) o una instrucción que especifique el nivel de acceso, como [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)o [Private](../modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="9f439-118">You must declare every member using a [Dim Statement](../statements/dim-statement.md) or a statement that specifies access level, such as [Public](../modifiers/public.md), [Friend](../modifiers/friend.md), or [Private](../modifiers/private.md).</span></span> <span data-ttu-id="9f439-119">Si utiliza una `Dim` instrucción, el nivel de acceso predeterminado es Public.</span><span class="sxs-lookup"><span data-stu-id="9f439-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="9f439-120">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="9f439-120">Programming Tips</span></span>

- <span data-ttu-id="9f439-121">**Consumo de memoria.**</span><span class="sxs-lookup"><span data-stu-id="9f439-121">**Memory Consumption.**</span></span> <span data-ttu-id="9f439-122">Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="9f439-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="9f439-123">Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración.</span><span class="sxs-lookup"><span data-stu-id="9f439-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="9f439-124">Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.</span><span class="sxs-lookup"><span data-stu-id="9f439-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="9f439-125">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="9f439-125">**Interop Considerations.**</span></span> <span data-ttu-id="9f439-126">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos definidos por el usuario en otros entornos no son compatibles con los tipos de estructura de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f439-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="9f439-127">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="9f439-127">**Widening.**</span></span> <span data-ttu-id="9f439-128">No hay ninguna conversión automática a o desde cualquier tipo de datos de estructura.</span><span class="sxs-lookup"><span data-stu-id="9f439-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="9f439-129">Puede definir operadores de conversión en la estructura mediante la [instrucción del operador](../statements/operator-statement.md)y puede declarar que cada operador de conversión sea `Widening` o `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="9f439-129">You can define conversion operators on your structure using the [Operator Statement](../statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="9f439-130">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="9f439-130">**Type Characters.**</span></span> <span data-ttu-id="9f439-131">Los tipos de datos de estructura no tienen un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="9f439-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="9f439-132">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="9f439-132">**Framework Type.**</span></span> <span data-ttu-id="9f439-133">No hay ningún tipo correspondiente en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f439-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="9f439-134">Todas las estructuras heredan de la clase .NET Framework <xref:System.ValueType?displayProperty=nameWithType> , pero ninguna estructura individual corresponde a <xref:System.ValueType?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9f439-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="9f439-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f439-135">Example</span></span>

<span data-ttu-id="9f439-136">El paradigma siguiente muestra el contorno de la declaración de una estructura.</span><span class="sxs-lookup"><span data-stu-id="9f439-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="9f439-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f439-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="9f439-138">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9f439-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="9f439-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="9f439-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="9f439-140">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="9f439-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="9f439-141">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9f439-141">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="9f439-142">Widening</span><span class="sxs-lookup"><span data-stu-id="9f439-142">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="9f439-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="9f439-143">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="9f439-144">Estructuras</span><span class="sxs-lookup"><span data-stu-id="9f439-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="9f439-145">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9f439-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
