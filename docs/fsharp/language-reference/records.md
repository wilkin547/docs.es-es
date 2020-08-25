---
title: Registros
description: 'Obtenga información sobre cómo los registros de F # representan agregados simples de valores con nombre, opcionalmente con miembros.'
ms.date: 08/15/2020
ms.openlocfilehash: a72c0f15b58407e7d759e2fb5a1b35a7fc0d29e3
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812359"
---
# <a name="records"></a><span data-ttu-id="e4ff9-103">Registros</span><span class="sxs-lookup"><span data-stu-id="e4ff9-103">Records</span></span>

<span data-ttu-id="e4ff9-104">Los registros representan agregados simples de valores con nombre, opcionalmente con miembros.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="e4ff9-105">Pueden ser Structs o tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="e4ff9-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4ff9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4ff9-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="e4ff9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4ff9-108">Remarks</span></span>

<span data-ttu-id="e4ff9-109">En la sintaxis anterior, *TypeName* es el nombre del tipo de registro, *Label1* y *Label2* son nombres de valores, denominados *etiquetas*, y *Type1* y *tipo2* son los tipos de estos valores.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="e4ff9-110">*member-List* es la lista opcional de miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="e4ff9-111">Puede usar el `[<Struct>]` atributo para crear un registro struct en lugar de un registro que sea un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="e4ff9-112">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="e4ff9-113">Cuando cada etiqueta está en una línea independiente, el punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="e4ff9-114">Puede establecer valores en expresiones conocidas como *expresiones de registro*.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="e4ff9-115">El compilador deduce el tipo a partir de las etiquetas utilizadas (si las etiquetas son suficientemente distintas de las de otros tipos de registro).</span><span class="sxs-lookup"><span data-stu-id="e4ff9-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="e4ff9-116">Las llaves ({}) incluyen la expresión de registro.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="e4ff9-117">En el código siguiente se muestra una expresión de registro que inicializa un registro con tres elementos Float con etiquetas `x` , `y` y `z` .</span><span class="sxs-lookup"><span data-stu-id="e4ff9-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="e4ff9-118">No utilice la forma abreviada si puede haber otro tipo que también tenga las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="e4ff9-119">Las etiquetas del tipo declarado más recientemente tienen prioridad sobre las del tipo declarado previamente, por lo que en el ejemplo anterior, `mypoint3D` se deduce que es `Point3D` .</span><span class="sxs-lookup"><span data-stu-id="e4ff9-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="e4ff9-120">Puede especificar explícitamente el tipo de registro, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="e4ff9-121">Los métodos se pueden definir para tipos de registro del mismo modo que para los tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="e4ff9-122">Crear registros mediante expresiones de registro</span><span class="sxs-lookup"><span data-stu-id="e4ff9-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="e4ff9-123">Puede inicializar los registros mediante las etiquetas definidas en el registro.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="e4ff9-124">Una expresión que hace esto se conoce como una *expresión de registro*.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="e4ff9-125">Use llaves para encerrar la expresión de registro y use el punto y coma como delimitador.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="e4ff9-126">En el ejemplo siguiente se muestra cómo crear un registro.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="e4ff9-127">Los signos de punto y coma después del último campo de la expresión de registro y de la definición de tipo son opcionales, independientemente de si todos los campos están en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="e4ff9-128">Al crear un registro, debe proporcionar valores para cada campo.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="e4ff9-129">No se puede hacer referencia a los valores de otros campos de la expresión de inicialización de ningún campo.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="e4ff9-130">En el código siguiente, el tipo de `myRecord2` se deduce de los nombres de los campos.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="e4ff9-131">Opcionalmente, puede especificar el nombre del tipo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="e4ff9-132">Otra forma de construcción de registros puede ser útil si tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="e4ff9-133">La siguiente línea de código ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="e4ff9-134">Esta forma de la expresión de registro se denomina *expresión de registro de copia y actualización*.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="e4ff9-135">Los registros son inmutables de forma predeterminada; sin embargo, puede crear fácilmente registros modificados mediante una expresión de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="e4ff9-136">También puede especificar explícitamente un campo mutable.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="e4ff9-137">No use el atributo DefaultValue con campos de registro.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="e4ff9-138">Un mejor enfoque es definir instancias predeterminadas de registros con campos que se inicializan con valores predeterminados y, a continuación, usar una expresión de registro de copia y actualización para establecer los campos que difieren de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

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

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="e4ff9-139">Crear registros recursivos mutuamente</span><span class="sxs-lookup"><span data-stu-id="e4ff9-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="e4ff9-140">En algún momento al crear un registro, puede que desee que dependa de otro tipo que le gustaría definir después.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="e4ff9-141">Se trata de un error de compilación a menos que defina los tipos de registro para que sean recursivos mutuamente.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="e4ff9-142">La definición de registros recursivos mutuamente se realiza con la `and` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="e4ff9-143">Esto le permite vincular 2 o más tipos de registro juntos.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="e4ff9-144">Por ejemplo, el código siguiente define un `Person` `Address` tipo y como recursivo mutuamente:</span><span class="sxs-lookup"><span data-stu-id="e4ff9-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

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

<span data-ttu-id="e4ff9-145">Si fuera a definir el ejemplo anterior sin la `and` palabra clave, no se compilaría.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="e4ff9-146">La `and` palabra clave es necesaria para las definiciones mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="e4ff9-147">Coincidencia de patrones con registros</span><span class="sxs-lookup"><span data-stu-id="e4ff9-147">Pattern Matching with Records</span></span>

<span data-ttu-id="e4ff9-148">Los registros se pueden usar con la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="e4ff9-149">Puede especificar algunos campos explícitamente y proporcionar variables para otros campos que se asignarán cuando se produzca una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="e4ff9-150">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="e4ff9-151">El resultado de este código es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a><span data-ttu-id="e4ff9-152">Registros y miembros</span><span class="sxs-lookup"><span data-stu-id="e4ff9-152">Records and members</span></span>

<span data-ttu-id="e4ff9-153">Puede especificar miembros en registros de forma muy parecida a como se hace con las clases.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-153">You can specify members on records much like you can with classes.</span></span> <span data-ttu-id="e4ff9-154">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-154">There is no support for fields.</span></span> <span data-ttu-id="e4ff9-155">Un enfoque común consiste en definir un `Default` miembro estático para facilitar la construcción de registros:</span><span class="sxs-lookup"><span data-stu-id="e4ff9-155">A common approach is to define a `Default` static member for easy record construction:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

<span data-ttu-id="e4ff9-156">Si utiliza un identificador propio, ese identificador hace referencia a la instancia del registro cuyo miembro se llama:</span><span class="sxs-lookup"><span data-stu-id="e4ff9-156">If you use a self identifier, that identifier refers to the instance of the record whose member is called:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123 }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="e4ff9-157">Diferencias entre los registros y las clases</span><span class="sxs-lookup"><span data-stu-id="e4ff9-157">Differences Between Records and Classes</span></span>

<span data-ttu-id="e4ff9-158">Los campos de registro difieren de las clases en que se exponen automáticamente como propiedades y se usan en la creación y copia de registros.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-158">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="e4ff9-159">La construcción de registros también difiere de la construcción de clases.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-159">Record construction also differs from class construction.</span></span> <span data-ttu-id="e4ff9-160">En un tipo de registro, no se puede definir un constructor.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-160">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="e4ff9-161">En su lugar, se aplica la sintaxis de construcción que se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-161">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="e4ff9-162">Las clases no tienen ninguna relación directa entre los parámetros de constructor, los campos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-162">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="e4ff9-163">Al igual que los tipos de estructura y Unión, los registros tienen una semántica estructural de igualdad.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-163">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="e4ff9-164">Las clases tienen semántica de igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-164">Classes have reference equality semantics.</span></span> <span data-ttu-id="e4ff9-165">El siguiente ejemplo de código muestra esto.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-165">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="e4ff9-166">El resultado de este código es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4ff9-166">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="e4ff9-167">Si escribe el mismo código con clases, los dos objetos de clase no serían iguales porque los dos valores representarían dos objetos en el montón y solo se compararían las direcciones (a menos que el tipo de clase invalide el `System.Object.Equals` método).</span><span class="sxs-lookup"><span data-stu-id="e4ff9-167">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="e4ff9-168">Si necesita igualdad de referencia para los registros, agregue el atributo `[<ReferenceEquality>]` encima del registro.</span><span class="sxs-lookup"><span data-stu-id="e4ff9-168">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ff9-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4ff9-169">See also</span></span>

- [<span data-ttu-id="e4ff9-170">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="e4ff9-170">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="e4ff9-171">Clases</span><span class="sxs-lookup"><span data-stu-id="e4ff9-171">Classes</span></span>](classes.md)
- [<span data-ttu-id="e4ff9-172">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e4ff9-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e4ff9-173">Igualdad de referencia</span><span class="sxs-lookup"><span data-stu-id="e4ff9-173">Reference-Equality</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-referenceequalityattribute.html)
- [<span data-ttu-id="e4ff9-174">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="e4ff9-174">Pattern Matching</span></span>](pattern-matching.md)
