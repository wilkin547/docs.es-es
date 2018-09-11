---
title: Registros (F#)
description: 'Obtenga información sobre cómo F # registros representan agregados simples de valores con nombre, opcionalmente con miembros.'
ms.date: 05/16/2016
ms.openlocfilehash: 6103d96b6b80a9e2ed168755958dbe800f7fa862
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44368221"
---
# <a name="records"></a><span data-ttu-id="eafaa-103">Registros</span><span class="sxs-lookup"><span data-stu-id="eafaa-103">Records</span></span>

<span data-ttu-id="eafaa-104">Los registros representan agregados simples de valores con nombre, opcionalmente con miembros.</span><span class="sxs-lookup"><span data-stu-id="eafaa-104">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="eafaa-105">A partir de F # 4.1, o bien pueden ser tipos de referencia o structs.</span><span class="sxs-lookup"><span data-stu-id="eafaa-105">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="eafaa-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eafaa-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="eafaa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eafaa-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="eafaa-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eafaa-108">Remarks</span></span>

<span data-ttu-id="eafaa-109">En la sintaxis anterior, *typename* es el nombre del tipo de registro, *label1* y *label2* son nombres de valores, que se conoce como *etiquetas*, y *type1* y *type2* son los tipos de estos valores.</span><span class="sxs-lookup"><span data-stu-id="eafaa-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="eafaa-110">*lista de miembros* es la lista opcional de miembros para el tipo.</span><span class="sxs-lookup"><span data-stu-id="eafaa-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="eafaa-111">Puede usar el `[<Struct>]` atributo para crear un registro de struct en lugar de un registro que es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="eafaa-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="eafaa-112">Estos son algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="eafaa-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="eafaa-113">Una vez cada etiqueta en una línea independiente, el punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="eafaa-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="eafaa-114">Puede establecer los valores en expresiones que se conoce como *grabar expresiones*.</span><span class="sxs-lookup"><span data-stu-id="eafaa-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="eafaa-115">El compilador deduce el tipo de las etiquetas que se usa (si las etiquetas son suficientemente distintas de los de otros tipos de registros).</span><span class="sxs-lookup"><span data-stu-id="eafaa-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="eafaa-116">Llaves ({}) contienen la expresión de registro.</span><span class="sxs-lookup"><span data-stu-id="eafaa-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="eafaa-117">El código siguiente muestra una expresión de registro que inicializa un registro con tres elementos float con etiquetas `x`, `y` y `z`.</span><span class="sxs-lookup"><span data-stu-id="eafaa-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="eafaa-118">No utilice la forma abreviada si podría haber otro tipo que también tiene las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="eafaa-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="eafaa-119">Las etiquetas del tipo declarado más recientemente tienen prioridad sobre las del tipo declarado previamente, por lo tanto en el ejemplo anterior, `mypoint3D` se infiere para ser `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="eafaa-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="eafaa-120">Puede especificar explícitamente el tipo de registro, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="eafaa-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="eafaa-121">Los métodos se pueden definir para los tipos de registros, como ocurre con los tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="eafaa-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="eafaa-122">Creación de registros mediante el uso de expresiones de registro</span><span class="sxs-lookup"><span data-stu-id="eafaa-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="eafaa-123">Puede inicializar los registros mediante el uso de las etiquetas que se definen en el registro.</span><span class="sxs-lookup"><span data-stu-id="eafaa-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="eafaa-124">Una expresión que hace esto se conoce como un *grabar expresión*.</span><span class="sxs-lookup"><span data-stu-id="eafaa-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="eafaa-125">Use llaves para incluir la expresión de registro y utilice el punto y coma como delimitador.</span><span class="sxs-lookup"><span data-stu-id="eafaa-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="eafaa-126">El ejemplo siguiente muestra cómo crear un registro.</span><span class="sxs-lookup"><span data-stu-id="eafaa-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="eafaa-127">El punto y coma después del último campo en la expresión de registro y en la definición de tipo es opcional, independientemente de si los campos están todas en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="eafaa-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="eafaa-128">Cuando se crea un registro, debe proporcionar valores para cada campo.</span><span class="sxs-lookup"><span data-stu-id="eafaa-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="eafaa-129">Los valores de otros campos en la expresión de inicialización para cualquier campo, no se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="eafaa-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="eafaa-130">En el código siguiente, el tipo de `myRecord2` se deduce de los nombres de los campos.</span><span class="sxs-lookup"><span data-stu-id="eafaa-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="eafaa-131">Si lo desea, puede especificar el nombre de tipo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="eafaa-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="eafaa-132">Otra forma de construcción de registro puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="eafaa-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="eafaa-133">Esto ilustra en la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="eafaa-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="eafaa-134">Este formulario de la expresión de registro se denomina el *copiar y actualizar la expresión de registro*.</span><span class="sxs-lookup"><span data-stu-id="eafaa-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="eafaa-135">Los registros son inmutables de manera predeterminada; Sin embargo, puede crear fácilmente los registros modificados mediante el uso de una expresión de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="eafaa-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="eafaa-136">Puede especificar explícitamente un campo mutable.</span><span class="sxs-lookup"><span data-stu-id="eafaa-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="eafaa-137">No use el atributo DefaultValue con campos de registro.</span><span class="sxs-lookup"><span data-stu-id="eafaa-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="eafaa-138">Un mejor enfoque consiste en definir las instancias predeterminadas de los registros con campos que se inicializan en valores predeterminados y, a continuación, usar una copia y actualizar la expresión de registro para establecer los campos que difieren de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="eafaa-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="eafaa-139">Coincidencia de patrones con registros</span><span class="sxs-lookup"><span data-stu-id="eafaa-139">Pattern Matching with Records</span></span>

<span data-ttu-id="eafaa-140">Registros pueden utilizarse con coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="eafaa-140">Records can be used with pattern matching.</span></span> <span data-ttu-id="eafaa-141">Puede especificar algunos campos explícitamente y proporcionar variables para otros campos que se asignará cuando se produce una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="eafaa-141">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="eafaa-142">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="eafaa-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="eafaa-143">El resultado de este código es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eafaa-143">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="eafaa-144">Diferencias entre clases y los registros</span><span class="sxs-lookup"><span data-stu-id="eafaa-144">Differences Between Records and Classes</span></span>

<span data-ttu-id="eafaa-145">Campos de registro difieren de las clases que automáticamente se exponen como propiedades, y se usan en la creación y copia de registros.</span><span class="sxs-lookup"><span data-stu-id="eafaa-145">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="eafaa-146">Construcción de registro también difiere de la construcción de la clase.</span><span class="sxs-lookup"><span data-stu-id="eafaa-146">Record construction also differs from class construction.</span></span> <span data-ttu-id="eafaa-147">En un tipo de registro, no se puede definir un constructor.</span><span class="sxs-lookup"><span data-stu-id="eafaa-147">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="eafaa-148">En su lugar, se aplica la sintaxis de construcción descrita en este tema.</span><span class="sxs-lookup"><span data-stu-id="eafaa-148">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="eafaa-149">Las clases no tienen ninguna relación directa entre los parámetros del constructor, campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="eafaa-149">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="eafaa-150">Al igual que los tipos de estructura y unión, los registros tienen semántica de igualdad estructural.</span><span class="sxs-lookup"><span data-stu-id="eafaa-150">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="eafaa-151">Las clases tienen referencia semántica de igualdad.</span><span class="sxs-lookup"><span data-stu-id="eafaa-151">Classes have reference equality semantics.</span></span> <span data-ttu-id="eafaa-152">El siguiente ejemplo de código muestra esto.</span><span class="sxs-lookup"><span data-stu-id="eafaa-152">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="eafaa-153">El resultado de este código es como sigue:</span><span class="sxs-lookup"><span data-stu-id="eafaa-153">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="eafaa-154">Si escribe el mismo código con clases, los dos objetos de clase sería desiguales porque los dos valores representarían dos objetos en el montón y se comparan solo las direcciones (a menos que el tipo de clase invalida el `System.Object.Equals` método).</span><span class="sxs-lookup"><span data-stu-id="eafaa-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="eafaa-155">Si necesita hacer referencia a la igualdad para los registros, agregue el atributo `[<ReferenceEquality>]` anteriormente el registro.</span><span class="sxs-lookup"><span data-stu-id="eafaa-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="eafaa-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="eafaa-156">See also</span></span>

- [<span data-ttu-id="eafaa-157">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="eafaa-157">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="eafaa-158">Clases</span><span class="sxs-lookup"><span data-stu-id="eafaa-158">Classes</span></span>](classes.md)
- [<span data-ttu-id="eafaa-159">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="eafaa-159">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="eafaa-160">Igualdad de referencia</span><span class="sxs-lookup"><span data-stu-id="eafaa-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="eafaa-161">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="eafaa-161">Pattern Matching</span></span>](pattern-matching.md)
