---
title: Registros
description: Obtenga información F# sobre cómo los registros representan agregados simples de valores con nombre, opcionalmente con miembros.
ms.date: 06/09/2019
ms.openlocfilehash: 874c5fa30a36f2778f7a43266316deb8c59d1d72
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216793"
---
# <a name="records"></a><span data-ttu-id="b2c55-103">Registros</span><span class="sxs-lookup"><span data-stu-id="b2c55-103">Records</span></span>

<span data-ttu-id="b2c55-104">Los registros representan agregados simples de valores con nombre, opcionalmente con miembros.</span><span class="sxs-lookup"><span data-stu-id="b2c55-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="b2c55-105">Pueden ser Structs o tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="b2c55-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="b2c55-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2c55-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2c55-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2c55-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="b2c55-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2c55-108">Remarks</span></span>

<span data-ttu-id="b2c55-109">En la sintaxis anterior, *TypeName* es el nombre del tipo de registro, *Label1* y *Label2* son nombres de valores, denominados *etiquetas*, y *Type1* y *tipo2* son los tipos de estos valores.</span><span class="sxs-lookup"><span data-stu-id="b2c55-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="b2c55-110">*member-List* es la lista opcional de miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="b2c55-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="b2c55-111">Puede usar el `[<Struct>]` atributo para crear un registro struct en lugar de un registro que sea un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="b2c55-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="b2c55-112">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b2c55-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="b2c55-113">Cuando cada etiqueta está en una línea independiente, el punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="b2c55-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="b2c55-114">Puede establecer valores en expresiones conocidas como *expresiones de registro*.</span><span class="sxs-lookup"><span data-stu-id="b2c55-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="b2c55-115">El compilador deduce el tipo a partir de las etiquetas utilizadas (si las etiquetas son suficientemente distintas de las de otros tipos de registro).</span><span class="sxs-lookup"><span data-stu-id="b2c55-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="b2c55-116">Las llaves ({}) incluyen la expresión de registro.</span><span class="sxs-lookup"><span data-stu-id="b2c55-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="b2c55-117">En el código siguiente se muestra una expresión de registro que inicializa un registro con tres elementos Float `x`con `y` etiquetas `z`, y.</span><span class="sxs-lookup"><span data-stu-id="b2c55-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="b2c55-118">No utilice la forma abreviada si puede haber otro tipo que también tenga las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="b2c55-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="b2c55-119">Las etiquetas del tipo declarado más recientemente tienen prioridad sobre las del tipo declarado previamente, por lo que en el ejemplo anterior, `mypoint3D` se deduce `Point3D`que es.</span><span class="sxs-lookup"><span data-stu-id="b2c55-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="b2c55-120">Puede especificar explícitamente el tipo de registro, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2c55-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="b2c55-121">Los métodos se pueden definir para tipos de registro del mismo modo que para los tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="b2c55-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="b2c55-122">Crear registros mediante expresiones de registro</span><span class="sxs-lookup"><span data-stu-id="b2c55-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="b2c55-123">Puede inicializar los registros mediante las etiquetas definidas en el registro.</span><span class="sxs-lookup"><span data-stu-id="b2c55-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="b2c55-124">Una expresión que hace esto se conoce como una *expresión de registro*.</span><span class="sxs-lookup"><span data-stu-id="b2c55-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="b2c55-125">Use llaves para encerrar la expresión de registro y use el punto y coma como delimitador.</span><span class="sxs-lookup"><span data-stu-id="b2c55-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="b2c55-126">En el ejemplo siguiente se muestra cómo crear un registro.</span><span class="sxs-lookup"><span data-stu-id="b2c55-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="b2c55-127">Los signos de punto y coma después del último campo de la expresión de registro y de la definición de tipo son opcionales, independientemente de si todos los campos están en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="b2c55-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="b2c55-128">Al crear un registro, debe proporcionar valores para cada campo.</span><span class="sxs-lookup"><span data-stu-id="b2c55-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="b2c55-129">No se puede hacer referencia a los valores de otros campos de la expresión de inicialización de ningún campo.</span><span class="sxs-lookup"><span data-stu-id="b2c55-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="b2c55-130">En el código siguiente, el tipo de `myRecord2` se deduce de los nombres de los campos.</span><span class="sxs-lookup"><span data-stu-id="b2c55-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="b2c55-131">Opcionalmente, puede especificar el nombre del tipo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b2c55-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="b2c55-132">Otra forma de construcción de registros puede ser útil si tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="b2c55-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="b2c55-133">La siguiente línea de código ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="b2c55-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="b2c55-134">Esta forma de la expresión de registro se denomina *expresión de registro de copia y actualización*.</span><span class="sxs-lookup"><span data-stu-id="b2c55-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="b2c55-135">Los registros son inmutables de forma predeterminada; sin embargo, puede crear fácilmente registros modificados mediante una expresión de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="b2c55-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="b2c55-136">También puede especificar explícitamente un campo mutable.</span><span class="sxs-lookup"><span data-stu-id="b2c55-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="b2c55-137">No use el atributo DefaultValue con campos de registro.</span><span class="sxs-lookup"><span data-stu-id="b2c55-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="b2c55-138">Un mejor enfoque es definir instancias predeterminadas de registros con campos que se inicializan con valores predeterminados y, a continuación, usar una expresión de registro de copia y actualización para establecer los campos que difieren de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b2c55-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

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

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="b2c55-139">Crear registros recursivos mutuamente</span><span class="sxs-lookup"><span data-stu-id="b2c55-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="b2c55-140">En algún momento al crear un registro, puede que desee que dependa de otro tipo que le gustaría definir después.</span><span class="sxs-lookup"><span data-stu-id="b2c55-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="b2c55-141">Se trata de un error de compilación a menos que defina los tipos de registro para que sean recursivos mutuamente.</span><span class="sxs-lookup"><span data-stu-id="b2c55-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="b2c55-142">La definición de registros recursivos mutuamente se realiza `and` con la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b2c55-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="b2c55-143">Esto le permite vincular 2 o más tipos de registro juntos.</span><span class="sxs-lookup"><span data-stu-id="b2c55-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="b2c55-144">Por ejemplo, el código siguiente define un `Person` tipo `Address` y como recursivo mutuamente:</span><span class="sxs-lookup"><span data-stu-id="b2c55-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="b2c55-145">Si fuera a definir el ejemplo anterior sin la `and` palabra clave, no se compilaría.</span><span class="sxs-lookup"><span data-stu-id="b2c55-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="b2c55-146">La `and` palabra clave es necesaria para las definiciones mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="b2c55-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="b2c55-147">Coincidencia de patrones con registros</span><span class="sxs-lookup"><span data-stu-id="b2c55-147">Pattern Matching with Records</span></span>

<span data-ttu-id="b2c55-148">Los registros se pueden usar con la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="b2c55-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="b2c55-149">Puede especificar algunos campos explícitamente y proporcionar variables para otros campos que se asignarán cuando se produzca una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="b2c55-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="b2c55-150">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b2c55-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="b2c55-151">El resultado de este código es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2c55-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="b2c55-152">Diferencias entre los registros y las clases</span><span class="sxs-lookup"><span data-stu-id="b2c55-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="b2c55-153">Los campos de registro difieren de las clases en que se exponen automáticamente como propiedades y se usan en la creación y copia de registros.</span><span class="sxs-lookup"><span data-stu-id="b2c55-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="b2c55-154">La construcción de registros también difiere de la construcción de clases.</span><span class="sxs-lookup"><span data-stu-id="b2c55-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="b2c55-155">En un tipo de registro, no se puede definir un constructor.</span><span class="sxs-lookup"><span data-stu-id="b2c55-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="b2c55-156">En su lugar, se aplica la sintaxis de construcción que se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="b2c55-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="b2c55-157">Las clases no tienen ninguna relación directa entre los parámetros de constructor, los campos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b2c55-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="b2c55-158">Al igual que los tipos de estructura y Unión, los registros tienen una semántica estructural de igualdad.</span><span class="sxs-lookup"><span data-stu-id="b2c55-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="b2c55-159">Las clases tienen semántica de igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="b2c55-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="b2c55-160">El siguiente ejemplo de código muestra esto.</span><span class="sxs-lookup"><span data-stu-id="b2c55-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="b2c55-161">El resultado de este código es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2c55-161">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="b2c55-162">Si escribe el mismo código con clases, los dos objetos de clase no serían iguales porque los dos valores representarían dos objetos en el montón y solo se compararían las direcciones (a menos que el tipo de `System.Object.Equals` clase invalide el método).</span><span class="sxs-lookup"><span data-stu-id="b2c55-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="b2c55-163">Si necesita igualdad de referencia para los registros, agregue el `[<ReferenceEquality>]` atributo encima del registro.</span><span class="sxs-lookup"><span data-stu-id="b2c55-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c55-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c55-164">See also</span></span>

- [<span data-ttu-id="b2c55-165">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="b2c55-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="b2c55-166">Clases</span><span class="sxs-lookup"><span data-stu-id="b2c55-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="b2c55-167">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="b2c55-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b2c55-168">Igualdad de referencia</span><span class="sxs-lookup"><span data-stu-id="b2c55-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="b2c55-169">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="b2c55-169">Pattern Matching</span></span>](pattern-matching.md)
