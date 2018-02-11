---
title: Tuplas en Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="9bca8-102">Tuplas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bca8-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="9bca8-103">A partir de Visual Basic de 2017, el lenguaje Visual Basic ofrece compatibilidad integrada para las tuplas que permite crear tuplas y acceder a los elementos de tuplas que sea más fácil.</span><span class="sxs-lookup"><span data-stu-id="9bca8-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="9bca8-104">Una tupla es una estructura de datos ligero que tiene un número específico y la secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="9bca8-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="9bca8-105">Al crear una instancia de la tupla, puede definir el número y el tipo de datos de cada valor (o elemento).</span><span class="sxs-lookup"><span data-stu-id="9bca8-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="9bca8-106">Por ejemplo, una tupla de 2 (o un par) tiene dos elementos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="9bca8-107">Podría ser el primero un `Boolean` valor, mientras que el segundo es un `String`.</span><span class="sxs-lookup"><span data-stu-id="9bca8-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="9bca8-108">Porque tuplas resulte sencillo almacenar varios valores en un único objeto, se usan a menudo como una forma sencilla de devolver varios valores de un método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bca8-109">La compatibilidad de tupla requiere el <xref:System.ValueTuple> tipo.</span><span class="sxs-lookup"><span data-stu-id="9bca8-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="9bca8-110">Si no está instalado el 4.7 de .NET Framework, debe agregar el paquete de NuGet `System.ValueTuple`, que se encuentra disponible en la Galería de NuGet.</span><span class="sxs-lookup"><span data-stu-id="9bca8-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="9bca8-111">Sin este paquete, puede obtener un error de compilación similar a "Tipo predefinido 'ValueTuple(Of,,,)' no está definido o importado."</span><span class="sxs-lookup"><span data-stu-id="9bca8-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="9bca8-112">Creación de instancias y utilizando una tupla</span><span class="sxs-lookup"><span data-stu-id="9bca8-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="9bca8-113">Para crear instancias de una tupla envolvente sus paréntesis de mensajería instantánea de valores delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="9bca8-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="9bca8-114">Cada uno de esos valores, a continuación, se convierte en un campo de la tupla.</span><span class="sxs-lookup"><span data-stu-id="9bca8-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="9bca8-115">Por ejemplo, el código siguiente define un triple (o una tupla de 3) con un `Date` como su primer valor, un `String` como su segundo y un `Boolean` como su tercer.</span><span class="sxs-lookup"><span data-stu-id="9bca8-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="9bca8-116">De forma predeterminada, el nombre de cada campo de una tupla consta de la cadena `Item` junto con la posición del campo basado en uno en la tupla.</span><span class="sxs-lookup"><span data-stu-id="9bca8-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="9bca8-117">Para esta tupla de 3, el `Date` campo es `Item1`, `String` campo es `Item2`y el `Boolean` campo es `Item3`.</span><span class="sxs-lookup"><span data-stu-id="9bca8-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="9bca8-118">El ejemplo siguiente muestra los valores de campos de la tupla que se crea una instancia en la línea anterior de código</span><span class="sxs-lookup"><span data-stu-id="9bca8-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="9bca8-119">Los campos de una tupla de Visual Basic son de lectura y escritura; una vez haya creado la instancia de una tupla, puede modificar sus valores.</span><span class="sxs-lookup"><span data-stu-id="9bca8-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="9bca8-120">En el ejemplo siguiente se modifica dos de los tres campos de la tupla creada en el ejemplo anterior y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="9bca8-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="9bca8-121">Creación de instancias y utilizando una tupla con nombre</span><span class="sxs-lookup"><span data-stu-id="9bca8-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="9bca8-122">En lugar de usar los nombres predeterminados para los campos de la tupla, puede crear instancias de un *denominado tupla* mediante la asignación de sus propios nombres de elementos de la tupla.</span><span class="sxs-lookup"><span data-stu-id="9bca8-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="9bca8-123">Campos de la tupla pueden tener acceso por sus nombres asignados *o* por sus nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9bca8-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="9bca8-124">En el ejemplo siguiente se crea una instancia de la misma tupla de 3 como anteriormente, salvo que nombra explícitamente el primer campo `EventDate`, el segundo `Name`y el tercero `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="9bca8-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="9bca8-125">A continuación, muestra los valores de campo, modifica y muestra los valores de campo nuevo.</span><span class="sxs-lookup"><span data-stu-id="9bca8-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="9bca8-126">Nombres de elementos de tupla deducido</span><span class="sxs-lookup"><span data-stu-id="9bca8-126">Inferred tuple element names</span></span>

<span data-ttu-id="9bca8-127">A partir de 15.3 de Visual Basic, Visual Basic puede deducir los nombres de elementos de tupla; no tienes que volver a asignarlos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9bca8-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="9bca8-128">Los nombres de tupla deducidos son útiles al inicializar una tupla a partir de un conjunto de variables y desea que el nombre del elemento de tupla para ser el mismo que el nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="9bca8-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="9bca8-129">En el ejemplo siguiente se crea un `stateInfo` tupla que contiene tres explícitamente denominado elementos, `state`, `stateName`, y `capital`.</span><span class="sxs-lookup"><span data-stu-id="9bca8-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="9bca8-130">Tenga en cuenta que, en el nombre de los elementos, la instrucción de inicialización de tupla simplemente asigna los elementos nombrados los valores de las variables con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9bca8-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="9bca8-131">Dado que los elementos y las variables tienen el mismo nombre, el compilador de Visual Basic puede deducir los nombres de los campos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9bca8-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="9bca8-132">Para habilitar los nombres de elementos de tupla interred, debe definir la versión del compilador de Visual Basic para usar en su proyecto de Visual Basic (\*.vbproj) archivo:</span><span class="sxs-lookup"><span data-stu-id="9bca8-132">To enable interred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="9bca8-133">Tuplas como valores devueltos del método</span><span class="sxs-lookup"><span data-stu-id="9bca8-133">Tuples as method return values</span></span>

<span data-ttu-id="9bca8-134">Un método puede devolver un solo valor.</span><span class="sxs-lookup"><span data-stu-id="9bca8-134">A method can return only a single value.</span></span> <span data-ttu-id="9bca8-135">Sin embargo, con frecuencia, desea que una llamada al método para devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="9bca8-135">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="9bca8-136">Hay varias formas de evitar esta limitación:</span><span class="sxs-lookup"><span data-stu-id="9bca8-136">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="9bca8-137">Puede crear una clase o estructura personalizada cuyas propiedades o campos representan los valores devueltos por el método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-137">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="9bca8-138">Por lo tanto, es una solución pesado; requiere que se defina un tipo personalizado cuyo único propósito es recuperar los valores de una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-138">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="9bca8-139">Puede devolver un solo valor desde el método y devolver los valores restantes pasando por referencia al método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-139">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="9bca8-140">Esto implica la sobrecarga de crear instancias de una variable y los riesgos que se sobrescriba accidentalmente el valor de la variable que se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="9bca8-140">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="9bca8-141">Puede utilizar una tupla, que proporciona una solución ligera para recuperar varios valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-141">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="9bca8-142">Por ejemplo, el **TryParse** métodos de devolución de .NET un `Boolean` valor que indica si la operación de análisis se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9bca8-142">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="9bca8-143">El resultado de la operación de análisis se devuelve en una variable que se pasa por referencia al método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-143">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="9bca8-144">Normalmente, una llamada a la un método de análisis como <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9bca8-144">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="9bca8-145">Podemos devolvemos una tupla de la operación de análisis si se incluyen la llamada a la <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método en el propio método.</span><span class="sxs-lookup"><span data-stu-id="9bca8-145">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="9bca8-146">En el ejemplo siguiente, `NumericLibrary.ParseInteger` llamadas el <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método y devuelve una tupla con dos elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="9bca8-146">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="9bca8-147">A continuación, puede llamar al método con un código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bca8-147">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="9bca8-148">Tuplas de Visual Basic y las tuplas en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bca8-148">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="9bca8-149">Una tupla de Visual Basic es una instancia de uno de los **System.ValueTuple** tipos genéricos, que se introdujeron en la 4.7 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bca8-149">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="9bca8-150">.NET Framework también incluye un conjunto de genérico **System.Tuple** clases.</span><span class="sxs-lookup"><span data-stu-id="9bca8-150">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="9bca8-151">Estas clases, no obstante, difieren de las tuplas de Visual Basic y **System.ValueTuple** tipos genéricos en una de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="9bca8-151">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="9bca8-152">Los elementos de la **tupla** clases son propiedades denominadas `Item1`, `Item2`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9bca8-152">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="9bca8-153">En Visual Basic tuplas y **ValueTuple** tipos de elementos de tupla son campos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-153">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="9bca8-154">No se puede asignar nombres descriptivos a los elementos de un **tupla** instancia o de un **ValueTuple** instancia.</span><span class="sxs-lookup"><span data-stu-id="9bca8-154">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="9bca8-155">Visual Basic permite asignar nombres a los que se comunican el significado de los campos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-155">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="9bca8-156">Las propiedades de un **tupla** instancia son de solo lectura; las tuplas son inmutables.</span><span class="sxs-lookup"><span data-stu-id="9bca8-156">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="9bca8-157">En Visual Basic tuplas y **ValueTuple** tipos, campos de tupla son de lectura y escritura; las tuplas son mutables.</span><span class="sxs-lookup"><span data-stu-id="9bca8-157">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="9bca8-158">La interfaz genérica **tupla** tipos son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="9bca8-158">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="9bca8-159">Uso de estas **tupla** significa asignar objetos de tipos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-159">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="9bca8-160">En rutas de acceso activas, esto puede suponer un importante impacto en el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9bca8-160">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="9bca8-161">Tuplas de Visual Basic y **ValueTuple** tipos son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="9bca8-161">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="9bca8-162">Métodos de extensión en la <xref:System.TupleExtensions> clase que sean fáciles de convertir entre tuplas de Visual Basic y .NET **tupla** objetos.</span><span class="sxs-lookup"><span data-stu-id="9bca8-162">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="9bca8-163">El **ToTuple** método convierte una tupla de Visual Basic .NET **tupla** objeto y el **ToValueTuple** método convierte .NET **tupla** objeto de una tupla de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9bca8-163">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="9bca8-164">En el ejemplo siguiente se crea una tupla, lo convierte en .NET **tupla** objeto y lo vuelve a convertir una tupla de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9bca8-164">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="9bca8-165">En el ejemplo a continuación, compara este tupla con el original para asegurarse de que son iguales.</span><span class="sxs-lookup"><span data-stu-id="9bca8-165">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9bca8-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bca8-166">See also</span></span>

[<span data-ttu-id="9bca8-167">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9bca8-167">Visual Basic Language Reference</span></span>](index.md)  
