---
title: Atributos
description: Obtenga información F# sobre cómo los atributos permiten aplicar metadatos a una construcción de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 1e42dc61d44f31930a7b34799f28a68a2db69c8c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504122"
---
# <a name="attributes"></a><span data-ttu-id="6df86-103">Atributos</span><span class="sxs-lookup"><span data-stu-id="6df86-103">Attributes</span></span>

<span data-ttu-id="6df86-104">Los atributos permiten aplicar metadatos a una construcción de programación.</span><span class="sxs-lookup"><span data-stu-id="6df86-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="6df86-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6df86-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="6df86-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6df86-106">Remarks</span></span>

<span data-ttu-id="6df86-107">En la sintaxis anterior, el *destino* es opcional y, si está presente, especifica el tipo de entidad de programa a la que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="6df86-108">Los valores válidos para el *destino* se muestran en la tabla que aparece más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="6df86-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="6df86-109">El *atributo-name* hace referencia al nombre (posiblemente calificado con espacios de nombres) de un tipo de atributo válido, con o sin el sufijo `Attribute` que normalmente se usa en los nombres de tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="6df86-110">Por ejemplo, el tipo `ObsoleteAttribute` se puede acortar a simplemente `Obsolete` en este contexto.</span><span class="sxs-lookup"><span data-stu-id="6df86-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="6df86-111">Los *argumentos* son los argumentos del constructor para el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="6df86-112">Si un atributo tiene un constructor sin parámetros, se pueden omitir la lista de argumentos y los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6df86-112">If an attribute has a parameterless constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="6df86-113">Los atributos admiten argumentos posicionales y argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="6df86-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="6df86-114">Los *argumentos posicionales* son argumentos que se usan en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="6df86-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="6df86-115">Se pueden usar argumentos con nombre si el atributo tiene propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="6df86-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="6df86-116">Puede establecerlos mediante la siguiente sintaxis en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="6df86-116">You can set these by using the following syntax in the argument list.</span></span>

```fsharp
property-name = property-value
```

<span data-ttu-id="6df86-117">Dichas inicializaciones de propiedad pueden estar en cualquier orden, pero deben seguir cualquier argumento posicional.</span><span class="sxs-lookup"><span data-stu-id="6df86-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="6df86-118">El siguiente es un ejemplo de un atributo que usa argumentos posicionales e inicializaciones de propiedad:</span><span class="sxs-lookup"><span data-stu-id="6df86-118">The following is an example of an attribute that uses positional arguments and property initializations:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="6df86-119">En este ejemplo, el atributo es `DllImportAttribute`, que se usa en forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="6df86-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="6df86-120">El primer argumento es un parámetro posicional y el segundo es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="6df86-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="6df86-121">Los atributos son una construcción de programación de .NET que permite asociar un objeto conocido como *atributo* a un tipo u otro elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="6df86-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="6df86-122">El elemento de programa al que se aplica un atributo se conoce como *destino de atributo*.</span><span class="sxs-lookup"><span data-stu-id="6df86-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="6df86-123">El atributo normalmente contiene metadatos sobre su destino.</span><span class="sxs-lookup"><span data-stu-id="6df86-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="6df86-124">En este contexto, los metadatos pueden ser cualquier dato sobre el tipo que no sea sus campos y miembros.</span><span class="sxs-lookup"><span data-stu-id="6df86-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="6df86-125">Los atributos F# de se pueden aplicar a las siguientes construcciones de programación: funciones, métodos, ensamblados, módulos, tipos (clases, registros, estructuras, interfaces, delegados, enumeraciones, uniones, etc.), constructores, propiedades, campos, parámetros, parámetros de tipo y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="6df86-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="6df86-126">No se permiten atributos en `let` enlaces dentro de clases, expresiones o expresiones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6df86-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="6df86-127">Normalmente, la declaración de atributo aparece directamente antes de la declaración del destino de atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="6df86-128">Se pueden usar varias declaraciones de atributos juntas, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6df86-128">Multiple attribute declarations can be used together, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="6df86-129">Puede consultar los atributos en tiempo de ejecución mediante la reflexión de .NET.</span><span class="sxs-lookup"><span data-stu-id="6df86-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="6df86-130">Puede declarar varios atributos individualmente, como en el ejemplo de código anterior, o puede declararlos en un conjunto de corchetes si usa un punto y coma para separar los atributos y constructores individuales, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6df86-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="6df86-131">Normalmente, los atributos encontrados incluyen el atributo `Obsolete`, atributos para las consideraciones de seguridad, atributos para la compatibilidad con COM, atributos relacionados con la propiedad del código y atributos que indican si un tipo se puede serializar.</span><span class="sxs-lookup"><span data-stu-id="6df86-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="6df86-132">En el siguiente ejemplo se muestra el uso del atributo `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="6df86-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="6df86-133">En el caso de los destinos de atributo `assembly` y `module`, aplique los atributos a un enlace de `do` de nivel superior en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6df86-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="6df86-134">Puede incluir la palabra `assembly` o `module` en la declaración de atributo, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6df86-134">You can include the word `assembly` or `module` in the attribute declaration, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="6df86-135">Si se omite el destino de atributo de un atributo aplicado a un enlace de `do` F# , el compilador intenta determinar el destino de atributo que tiene sentido para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="6df86-136">Muchas clases de atributos tienen un atributo de tipo `System.AttributeUsageAttribute` que incluye información sobre los posibles destinos admitidos para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="6df86-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="6df86-137">Si el `System.AttributeUsageAttribute` indica que el atributo admite funciones como destinos, se toma el atributo para aplicar al punto de entrada principal del programa.</span><span class="sxs-lookup"><span data-stu-id="6df86-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="6df86-138">Si el `System.AttributeUsageAttribute` indica que el atributo admite ensamblados como destinos, el compilador toma el atributo para aplicar al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6df86-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="6df86-139">La mayoría de los atributos no se aplican a las funciones y los ensamblados, pero en los casos en que lo hacen, el atributo se toma para aplicarse a la función principal del programa.</span><span class="sxs-lookup"><span data-stu-id="6df86-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="6df86-140">Si el destino del atributo se especifica explícitamente, el atributo se aplica al destino especificado.</span><span class="sxs-lookup"><span data-stu-id="6df86-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="6df86-141">Aunque normalmente no es necesario especificar explícitamente el destino de atributo, en la tabla siguiente se muestran los valores válidos para el *destino* en un atributo junto con ejemplos de uso:</span><span class="sxs-lookup"><span data-stu-id="6df86-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute along with examples of usage are shown in the following table:</span></span>

<table>
  <tr>
    <th><span data-ttu-id="6df86-142">Destino de atributo</span><span class="sxs-lookup"><span data-stu-id="6df86-142">Attribute target</span></span></td>
    <th><span data-ttu-id="6df86-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6df86-143">Example</span></span></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-144">ensamblado</span><span class="sxs-lookup"><span data-stu-id="6df86-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-145">return</span><span class="sxs-lookup"><span data-stu-id="6df86-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-146">campo</span><span class="sxs-lookup"><span data-stu-id="6df86-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-147">propiedad</span><span class="sxs-lookup"><span data-stu-id="6df86-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-148">param</span><span class="sxs-lookup"><span data-stu-id="6df86-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="6df86-149">type</span><span class="sxs-lookup"><span data-stu-id="6df86-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="6df86-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6df86-150">See also</span></span>

- [<span data-ttu-id="6df86-151">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="6df86-151">F# Language Reference</span></span>](index.md)
