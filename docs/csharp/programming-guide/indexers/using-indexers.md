---
title: 'Uso de indizadores: Guía de programación de C#'
description: Aprenda a declarar y usar un indexador para una clase, estructura o interfaz en C#. En este artículo se incluye código de ejemplo.
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: a8a9e05c1d2e44841177a924c6ff51c6c9e6a05a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301871"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="02516-104">Uso de indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="02516-104">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="02516-105">Los indizadores son una comodidad sintáctica que le permiten crear una [clase](../../language-reference/keywords/class.md), [estructura](../../language-reference/builtin-types/struct.md) o [interfaz](../../language-reference/keywords/interface.md) a la que las aplicaciones cliente pueden acceder como una matriz.</span><span class="sxs-lookup"><span data-stu-id="02516-105">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="02516-106">El compilador generará una propiedad `Item` (o una propiedad con otro nombre si está presente <xref:System.Runtime.CompilerServices.IndexerNameAttribute>) y los métodos de descriptor de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="02516-106">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="02516-107">Los indexadores se implementan con más frecuencia en tipos cuyo propósito principal consiste en encapsular una matriz o colección interna.</span><span class="sxs-lookup"><span data-stu-id="02516-107">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="02516-108">Por ejemplo, imagine que tiene una clase `TempRecord` que representa la temperatura en grados Fahrenheit que se registra en 10 momentos diferentes durante un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="02516-108">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="02516-109">La clase contiene una matriz `temps` de tipo `float[]` para almacenar los valores de temperatura.</span><span class="sxs-lookup"><span data-stu-id="02516-109">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="02516-110">Si implementa un indizador en esta clase, los clientes pueden tener acceso a las temperaturas en una instancia de `TempRecord` como `float temp = tempRecord[4]` en lugar de como `float temp = tempRecord.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="02516-110">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="02516-111">La notación del indizador no solo simplifica la sintaxis para las aplicaciones cliente; también hace que la clase y su finalidad sean más intuitivas para que otros desarrolladores las entiendan.</span><span class="sxs-lookup"><span data-stu-id="02516-111">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="02516-112">Para declarar un indizador en una clase o un struct, use la palabra clave [this](../../language-reference/keywords/this.md), como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02516-112">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="02516-113">Al declarar un indizador, se generará automáticamente una propiedad denominada `Item` en el objeto.</span><span class="sxs-lookup"><span data-stu-id="02516-113">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="02516-114">No se puede acceder directamente a la propiedad `Item` desde la instancia de [expresión de acceso a miembros](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span><span class="sxs-lookup"><span data-stu-id="02516-114">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="02516-115">Además, si agrega una propiedad `Item` propia a un objeto con un indizador, obtendrá un [error del compilador CS0102](../../misc/cs0102.md).</span><span class="sxs-lookup"><span data-stu-id="02516-115">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="02516-116">Para evitar este error, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute> para cambiar el nombre del indizador como se detalla a continuación.</span><span class="sxs-lookup"><span data-stu-id="02516-116">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="02516-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02516-117">Remarks</span></span>

<span data-ttu-id="02516-118">Los tipos de un indexador y de sus parámetros deben ser al menos igual de accesibles que el propio indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-118">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="02516-119">Para obtener más información sobre los niveles de accesibilidad, vea [Modificadores de acceso](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="02516-119">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="02516-120">Para obtener más información sobre cómo usar los indexadores con una interfaz, vea [Indizadores en interfaces](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="02516-120">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="02516-121">La firma de un indexador consta del número y los tipos de sus parámetros formales.</span><span class="sxs-lookup"><span data-stu-id="02516-121">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="02516-122">No incluye el tipo de indizador ni los nombres de los parámetros formales.</span><span class="sxs-lookup"><span data-stu-id="02516-122">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="02516-123">Si declara más de un indexador en la misma clase, deben tener firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="02516-123">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="02516-124">Un valor de indexador no está clasificado como una variable; por tanto, no se puede pasar un valor de indexador como un parámetro [ref](../../language-reference/keywords/ref.md) u [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="02516-124">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="02516-125">Para proporcionar el indizador con un nombre que puedan usar otros lenguajes, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="02516-125">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="02516-126">Este indizador tendrá el nombre `TheItem`, ya que lo reemplaza el atributo de nombre del indizador.</span><span class="sxs-lookup"><span data-stu-id="02516-126">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="02516-127">De forma predeterminada, el nombre del indizador es `Item`.</span><span class="sxs-lookup"><span data-stu-id="02516-127">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="02516-128">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="02516-128">Example 1</span></span>

<span data-ttu-id="02516-129">En el ejemplo siguiente, se muestra cómo declarar un campo de matriz privada, `temps`, como un indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-129">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="02516-130">El indexador permite el acceso directo a la instancia `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="02516-130">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="02516-131">La alternativa a usar el indexador es declarar la matriz como un miembro [public](../../language-reference/keywords/public.md) y tener acceso directamente a sus miembros `tempRecord.temps[i]`.</span><span class="sxs-lookup"><span data-stu-id="02516-131">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="02516-132">Tenga en cuenta que, cuando se evalúa el acceso de un indexador (por ejemplo, en una instrucción `Console.Write`), se invoca al descriptor de acceso [get](../../language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="02516-132">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="02516-133">Por tanto, si no hay ningún descriptor de acceso `get`, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="02516-133">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="02516-134">Indexación con otros valores</span><span class="sxs-lookup"><span data-stu-id="02516-134">Indexing using other values</span></span>

<span data-ttu-id="02516-135">C# no limita el tipo de parámetro indizador a un entero.</span><span class="sxs-lookup"><span data-stu-id="02516-135">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="02516-136">Por ejemplo, puede ser útil usar una cadena con un indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-136">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="02516-137">Este tipo de indexador podría implementarse al buscar la cadena de la colección y devolver el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="02516-137">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="02516-138">Como los descriptores de acceso se pueden sobrecargar, pueden coexistir las versiones de cadena y entero.</span><span class="sxs-lookup"><span data-stu-id="02516-138">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="02516-139">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="02516-139">Example 2</span></span>

<span data-ttu-id="02516-140">En el ejemplo siguiente se declara una clase que almacena los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="02516-140">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="02516-141">Un descriptor de acceso `get` toma una cadena, el nombre de un día, y devuelve el entero correspondiente.</span><span class="sxs-lookup"><span data-stu-id="02516-141">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="02516-142">Por ejemplo, "Sunday" devuelve 0, "Monday" devuelve 1 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="02516-142">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="02516-143">Ejemplo de consumo 2</span><span class="sxs-lookup"><span data-stu-id="02516-143">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="02516-144">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="02516-144">Example 3</span></span>

<span data-ttu-id="02516-145">En el ejemplo siguiente se declara una clase que almacena los días de la semana mediante la enumeración <xref:System.DayOfWeek?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="02516-145">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="02516-146">Un descriptor de acceso `get` toma un valor `DayOfWeek`, el nombre de un día, y devuelve el entero correspondiente.</span><span class="sxs-lookup"><span data-stu-id="02516-146">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="02516-147">Por ejemplo, `DayOfWeek.Sunday` devuelve 0, `DayOfWeek.Monday` devuelve 1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="02516-147">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="02516-148">Ejemplo de consumo 3</span><span class="sxs-lookup"><span data-stu-id="02516-148">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="02516-149">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="02516-149">Robust programming</span></span>

<span data-ttu-id="02516-150">Hay dos formas principales en que se pueden mejorar la seguridad y confiabilidad de los indexadores:</span><span class="sxs-lookup"><span data-stu-id="02516-150">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="02516-151">Asegúrese de incorporar algún tipo de estrategia de control de errores para controlar la posibilidad de que el código de cliente pase un valor de índice no válido.</span><span class="sxs-lookup"><span data-stu-id="02516-151">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="02516-152">En el primer ejemplo de este tema, la clase TempRecord proporciona una propiedad Length que permite al código de cliente comprobar la entrada antes de pasarla al indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-152">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="02516-153">También puede colocar el código de control de errores en el propio indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-153">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="02516-154">Asegúrese de documentar para los usuarios cualquier excepción que se produzca dentro de un descriptor de acceso del indexador.</span><span class="sxs-lookup"><span data-stu-id="02516-154">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="02516-155">Establezca la accesibilidad de los descriptores de acceso [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) para que sea tan restrictiva como razonable.</span><span class="sxs-lookup"><span data-stu-id="02516-155">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="02516-156">Esto es importante para el descriptor de acceso `set` en particular.</span><span class="sxs-lookup"><span data-stu-id="02516-156">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="02516-157">Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="02516-157">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02516-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="02516-158">See also</span></span>

- [<span data-ttu-id="02516-159">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="02516-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="02516-160">Indizadores</span><span class="sxs-lookup"><span data-stu-id="02516-160">Indexers</span></span>](./index.md)
- [<span data-ttu-id="02516-161">Propiedades</span><span class="sxs-lookup"><span data-stu-id="02516-161">Properties</span></span>](../classes-and-structs/properties.md)
