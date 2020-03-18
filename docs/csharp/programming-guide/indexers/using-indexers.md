---
title: 'Uso de indizadores: Guía de programación de C#'
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 17162a0dc959a85c03a5cb5757e2b91fe10b0ab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628168"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="fa512-102">Uso de indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fa512-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="fa512-103">Los indexadores son una comodidad sintáctica que le permiten crear una [clase](../../language-reference/keywords/class.md), un [struct](../../language-reference/builtin-types/struct.md) o una [interfaz](../../language-reference/keywords/interface.md) a los que pueden acceder las aplicaciones cliente simplemente como una matriz.</span><span class="sxs-lookup"><span data-stu-id="fa512-103">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="fa512-104">Los indexadores se implementan con más frecuencia en tipos cuyo propósito principal consiste en encapsular una matriz o colección interna.</span><span class="sxs-lookup"><span data-stu-id="fa512-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="fa512-105">Por ejemplo, suponga que tiene una clase `TempRecord` que representa la temperatura en grados Fahrenheit que se registra en 10 momentos diferentes durante un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="fa512-105">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="fa512-106">La clase contiene una matriz `temps` de tipo `float[]` para almacenar los valores de temperatura.</span><span class="sxs-lookup"><span data-stu-id="fa512-106">The class contains an array `temps` of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="fa512-107">Si implementa un indizador en esta clase, los clientes pueden tener acceso a las temperaturas en una instancia de `TempRecord` como `float temp = tr[4]` en lugar de como `float temp = tr.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="fa512-107">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="fa512-108">La notación del indexador no solo simplifica la sintaxis para las aplicaciones cliente; también hace que la clase y su finalidad sean más intuitivas para que las conozcan otros desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="fa512-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
<span data-ttu-id="fa512-109">Para declarar un indizador en una clase o un struct, use la palabra clave [this](../../language-reference/keywords/this.md), como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa512-109">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a><span data-ttu-id="fa512-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa512-110">Remarks</span></span>

<span data-ttu-id="fa512-111">Los tipos de un indexador y de sus parámetros deben ser al menos igual de accesibles que el propio indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="fa512-112">Para obtener más información sobre los niveles de accesibilidad, vea [Modificadores de acceso](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="fa512-112">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="fa512-113">Para obtener más información sobre cómo usar los indexadores con una interfaz, vea [Indizadores en interfaces](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="fa512-113">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="fa512-114">La firma de un indexador consta del número y los tipos de sus parámetros formales.</span><span class="sxs-lookup"><span data-stu-id="fa512-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="fa512-115">No incluye el tipo de indizador ni los nombres de los parámetros formales.</span><span class="sxs-lookup"><span data-stu-id="fa512-115">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="fa512-116">Si declara más de un indexador en la misma clase, deben tener firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="fa512-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="fa512-117">Un valor de indexador no está clasificado como una variable; por tanto, no se puede pasar un valor de indexador como un parámetro [ref](../../language-reference/keywords/ref.md) u [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="fa512-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>  
  
 <span data-ttu-id="fa512-118">Para proporcionar el indizador con un nombre que puedan usar otros lenguajes, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa512-118">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

<span data-ttu-id="fa512-119">Este indexador tendrá el nombre `TheItem`.</span><span class="sxs-lookup"><span data-stu-id="fa512-119">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="fa512-120">Si no se proporciona el atributo de nombre, `Item` será el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fa512-120">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="fa512-121">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="fa512-121">Example 1</span></span>  
  
<span data-ttu-id="fa512-122">En el ejemplo siguiente, se muestra cómo declarar un campo de matriz privada, `temps`, como un indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-122">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="fa512-123">El indexador permite el acceso directo a la instancia `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="fa512-123">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="fa512-124">La alternativa a usar el indexador es declarar la matriz como un miembro [public](../../language-reference/keywords/public.md) y tener acceso directamente a sus miembros `tempRecord.temps[i]`.</span><span class="sxs-lookup"><span data-stu-id="fa512-124">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="fa512-125">Tenga en cuenta que, cuando se evalúa el acceso de un indexador (por ejemplo, en una instrucción `Console.Write`), se invoca al descriptor de acceso [get](../../language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="fa512-125">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="fa512-126">Por tanto, si no hay ningún descriptor de acceso `get`, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="fa512-126">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#1)]  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="fa512-127">Indexación con otros valores</span><span class="sxs-lookup"><span data-stu-id="fa512-127">Indexing using other values</span></span>

<span data-ttu-id="fa512-128">C# no limita el tipo de parámetro indizador a un entero.</span><span class="sxs-lookup"><span data-stu-id="fa512-128">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="fa512-129">Por ejemplo, puede ser útil usar una cadena con un indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-129">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="fa512-130">Este tipo de indexador podría implementarse al buscar la cadena de la colección y devolver el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="fa512-130">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="fa512-131">Ya que los descriptores de acceso se pueden sobrecargar, las versiones de cadena y entero pueden coexistir.</span><span class="sxs-lookup"><span data-stu-id="fa512-131">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="fa512-132">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="fa512-132">Example 2</span></span>  
  
<span data-ttu-id="fa512-133">En el ejemplo siguiente se declara una clase que almacena los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="fa512-133">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="fa512-134">Un descriptor de acceso `get` toma una cadena, el nombre de un día, y devuelve el entero correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fa512-134">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="fa512-135">Por ejemplo, "Sunday" devuelve 0, "Monday" devuelve 1 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="fa512-135">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fa512-136">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fa512-136">Robust programming</span></span>

 <span data-ttu-id="fa512-137">Hay dos formas principales en que se pueden mejorar la seguridad y confiabilidad de los indexadores:</span><span class="sxs-lookup"><span data-stu-id="fa512-137">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
- <span data-ttu-id="fa512-138">Asegúrese de incorporar algún tipo de estrategia de control de errores para controlar la posibilidad de que el código de cliente pase un valor de índice no válido.</span><span class="sxs-lookup"><span data-stu-id="fa512-138">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="fa512-139">En el primer ejemplo de este tema, la clase TempRecord proporciona una propiedad Length que permite al código de cliente comprobar la entrada antes de pasarla al indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-139">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="fa512-140">También puede colocar el código de control de errores en el propio indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-140">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="fa512-141">Asegúrese de documentar para los usuarios cualquier excepción que se produzca dentro de un descriptor de acceso del indexador.</span><span class="sxs-lookup"><span data-stu-id="fa512-141">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
- <span data-ttu-id="fa512-142">Establezca la accesibilidad de los descriptores de acceso [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) para que sea tan restrictiva como razonable.</span><span class="sxs-lookup"><span data-stu-id="fa512-142">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="fa512-143">Esto es importante para el descriptor de acceso `set` en particular.</span><span class="sxs-lookup"><span data-stu-id="fa512-143">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="fa512-144">Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="fa512-144">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa512-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa512-145">See also</span></span>

- [<span data-ttu-id="fa512-146">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fa512-146">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fa512-147">Indizadores</span><span class="sxs-lookup"><span data-stu-id="fa512-147">Indexers</span></span>](./index.md)
- [<span data-ttu-id="fa512-148">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fa512-148">Properties</span></span>](../classes-and-structs/properties.md)
