---
title: Atributos
description: Obtenga información sobre cómo F# atributos permiten que los metadatos que se aplicará a una construcción de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 6e80bc4e32ee4ff5ff132270bde8e2fd018369e1
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464663"
---
# <a name="attributes"></a><span data-ttu-id="47aab-103">Atributos</span><span class="sxs-lookup"><span data-stu-id="47aab-103">Attributes</span></span>

<span data-ttu-id="47aab-104">Atributos permiten que los metadatos que se aplicará a una construcción de programación.</span><span class="sxs-lookup"><span data-stu-id="47aab-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="47aab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47aab-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="47aab-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47aab-106">Remarks</span></span>

<span data-ttu-id="47aab-107">En la sintaxis anterior, el *destino* es opcional y, si está presente, especifica el tipo de entidad de programa que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="47aab-108">Los valores válidos para *destino* se muestran en la tabla que aparece más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="47aab-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="47aab-109">El *nombre del atributo* hace referencia al nombre (posiblemente calificado con espacios de nombres) de un tipo de atributo válido, con o sin el sufijo `Attribute` que normalmente se usa en nombres de tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="47aab-110">Por ejemplo, el tipo `ObsoleteAttribute` puede abreviar a `Obsolete` en este contexto.</span><span class="sxs-lookup"><span data-stu-id="47aab-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="47aab-111">El *argumentos* son los argumentos al constructor del tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="47aab-112">Si un atributo tiene un constructor predeterminado, se pueden omitir la lista de argumentos y los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="47aab-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="47aab-113">Los atributos admiten argumentos posicionales y argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="47aab-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="47aab-114">*Los argumentos posicionales* son argumentos que se usan en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="47aab-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="47aab-115">Pueden utilizar argumentos con nombre si el atributo tiene propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="47aab-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="47aab-116">Puede establecer estas opciones mediante la sintaxis siguiente en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="47aab-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="47aab-117">Inicializaciones de propiedad pueden estar en cualquier orden, pero deben seguir los argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="47aab-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="47aab-118">La siguiente es un ejemplo de un atributo que usa argumentos posicionales e inicializaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="47aab-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="47aab-119">En este ejemplo, el atributo es `DllImportAttribute`, aquí se usa en forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="47aab-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="47aab-120">El primer argumento es un parámetro de posición y el segundo es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="47aab-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="47aab-121">Los atributos son una construcción de programación de .NET que permite a un objeto que se conoce como un *atributo* va a asociar a un tipo u otro elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="47aab-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="47aab-122">El elemento de programa al que se aplica un atributo se conoce como el *destino del atributo*.</span><span class="sxs-lookup"><span data-stu-id="47aab-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="47aab-123">Normalmente, el atributo contiene metadatos acerca de su destino.</span><span class="sxs-lookup"><span data-stu-id="47aab-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="47aab-124">En este contexto, los metadatos podrían ser ningún dato sobre el tipo que no sean sus campos y los miembros.</span><span class="sxs-lookup"><span data-stu-id="47aab-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="47aab-125">Los atributos F# se pueden aplicar a las construcciones de programación siguientes: funciones, métodos, ensamblados, módulos, tipos (clases, registros, estructuras, interfaces, delegados, enumeraciones, uniones etc.), constructores, propiedades, campos, los parámetros, escriba los parámetros y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="47aab-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="47aab-126">No se admiten atributos en `let` enlaces dentro de clases, las expresiones o expresiones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="47aab-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="47aab-127">Normalmente, la declaración de atributos aparece directamente antes de la declaración del destino del atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="47aab-128">Juntos, como se indica a continuación, se pueden usar varias declaraciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="47aab-129">Puede consultar los atributos en tiempo de ejecución mediante la reflexión. NET.</span><span class="sxs-lookup"><span data-stu-id="47aab-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="47aab-130">Puede declarar varios atributos individualmente, como se muestra en el ejemplo de código anterior, o bien puede declarar en un conjunto de corchetes si usa un punto y coma para separar los atributos individuales y los constructores, como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="47aab-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="47aab-131">Atributos encontrados normalmente incluyen la `Obsolete` atributo, los atributos de las consideraciones de seguridad, los atributos para la compatibilidad con COM, atributos relacionados con la propiedad del código y los atributos que indica si se puede serializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="47aab-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="47aab-132">En el ejemplo siguiente se muestra el uso de la `Obsolete` atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="47aab-133">Para los destinos de atributo `assembly` y `module`, aplicar los atributos a un nivel superior `do` enlace en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47aab-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="47aab-134">Puede incluir la palabra `assembly` o `module` en la declaración de atributo, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="47aab-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="47aab-135">Si se omite el destino del atributo para un atributo aplicado a un `do` enlace, el F# compilador intenta determinar el destino del atributo que tenga sentido para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="47aab-136">Muchas clases de atributos tienen un atributo de tipo `System.AttributeUsageAttribute` que incluye información sobre los posibles destinos admitidos para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="47aab-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="47aab-137">Si el `System.AttributeUsageAttribute` indica que el atributo admite funciones como destinos, se obtendrá el atributo que se aplicará al punto de entrada principal del programa.</span><span class="sxs-lookup"><span data-stu-id="47aab-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="47aab-138">Si el `System.AttributeUsageAttribute` indica que el atributo admite ensamblados como destinos, el compilador usa el atributo se aplique al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47aab-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="47aab-139">La mayoría de los atributos no se aplican a las funciones y ensamblados, pero en los casos donde lo hacen, se toma el atributo que se aplicará a la función principal del programa.</span><span class="sxs-lookup"><span data-stu-id="47aab-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="47aab-140">Si el destino del atributo se especifica explícitamente, el atributo se aplica al destino especificado.</span><span class="sxs-lookup"><span data-stu-id="47aab-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="47aab-141">Aunque normalmente no es necesario especificar el atributo de destino explícitamente, los valores válidos para *destino* en un atributo que se muestran en la siguiente tabla, junto con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="47aab-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="47aab-142">Destino de atributo</span><span class="sxs-lookup"><span data-stu-id="47aab-142">Attribute target</span></span></td>
    <th><span data-ttu-id="47aab-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47aab-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-144">ensamblado</span><span class="sxs-lookup"><span data-stu-id="47aab-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-145">return</span><span class="sxs-lookup"><span data-stu-id="47aab-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-146">campo</span><span class="sxs-lookup"><span data-stu-id="47aab-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-147">propiedad</span><span class="sxs-lookup"><span data-stu-id="47aab-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-148">param</span><span class="sxs-lookup"><span data-stu-id="47aab-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="47aab-149">type</span><span class="sxs-lookup"><span data-stu-id="47aab-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="47aab-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="47aab-150">See also</span></span>

- [<span data-ttu-id="47aab-151">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="47aab-151">F# Language Reference</span></span>](index.md)