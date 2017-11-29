---
title: Atributos (F#)
description: "Obtenga información acerca de cómo F # atributos permiten que los metadatos que se aplicará a una construcción de programación."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a><span data-ttu-id="024d7-104">Atributos</span><span class="sxs-lookup"><span data-stu-id="024d7-104">Attributes</span></span>

<span data-ttu-id="024d7-105">Atributos permiten que los metadatos que se aplicará a una construcción de programación.</span><span class="sxs-lookup"><span data-stu-id="024d7-105">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="024d7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="024d7-106">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="024d7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="024d7-107">Remarks</span></span>

<span data-ttu-id="024d7-108">En la sintaxis anterior, el *destino* es opcional y, si está presente, especifica el tipo de entidad de programa que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-108">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="024d7-109">Los valores válidos para *destino* se muestran en la tabla que aparece más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="024d7-109">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="024d7-110">El *nombre del atributo* hace referencia al nombre (posiblemente calificado con espacios de nombres) de un tipo de atributo válido, con o sin el sufijo `Attribute` que normalmente se usa en nombres de tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-110">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="024d7-111">Por ejemplo, el tipo `ObsoleteAttribute` se puede abreviar simplemente `Obsolete` en este contexto.</span><span class="sxs-lookup"><span data-stu-id="024d7-111">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="024d7-112">El *argumentos* son los argumentos para el constructor para el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-112">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="024d7-113">Si un atributo tiene un constructor predeterminado, se pueden omitir la lista de argumentos y los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="024d7-113">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="024d7-114">Los atributos admiten argumentos posicionales y argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="024d7-114">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="024d7-115">*Argumentos posicionales* son los argumentos que se utilizan en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="024d7-115">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="024d7-116">Argumentos con nombre se pueden utilizar si el atributo tiene propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="024d7-116">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="024d7-117">Puede establecer estas opciones mediante la sintaxis siguiente en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="024d7-117">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="024d7-118">Dichas inicializaciones de propiedad pueden estar en cualquier orden, pero debe seguir los argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="024d7-118">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="024d7-119">Aquí te mostramos un ejemplo de un atributo que utiliza argumentos posicionales e inicializaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="024d7-119">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="024d7-120">En este ejemplo, el atributo es `DllImportAttribute`, aquí se utiliza en forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="024d7-120">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="024d7-121">El primer argumento es un parámetro posicional y el segundo es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="024d7-121">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="024d7-122">Los atributos son una construcción de programación de .NET que permite a un objeto que se conoce como un *atributo* asociarse con un tipo u otro elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="024d7-122">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="024d7-123">El elemento de programa al que se aplica un atributo se conoce como el *destino del atributo*.</span><span class="sxs-lookup"><span data-stu-id="024d7-123">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="024d7-124">El atributo suele contener metadatos acerca de su destino.</span><span class="sxs-lookup"><span data-stu-id="024d7-124">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="024d7-125">En este contexto, los metadatos podrían ser cualquier dato sobre el tipo, excepto sus campos y miembros.</span><span class="sxs-lookup"><span data-stu-id="024d7-125">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="024d7-126">Atributos en F # se pueden aplicar a las construcciones de programación siguientes: funciones, métodos, ensamblados, módulos, tipos (clases, registros, estructuras, interfaces, delegados, enumeraciones, uniones etc.), constructores, propiedades, campos, parámetros, parámetros de tipo y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="024d7-126">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="024d7-127">No se permiten atributos en `let` enlaces dentro de las clases, las expresiones o expresiones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="024d7-127">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="024d7-128">Normalmente, la declaración de atributos aparece directamente antes de la declaración del destino del atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-128">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="024d7-129">Varias declaraciones de atributo se pueden utilizar juntos, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="024d7-129">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="024d7-130">Puede consultar los atributos en tiempo de ejecución utilizando la reflexión. NET.</span><span class="sxs-lookup"><span data-stu-id="024d7-130">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="024d7-131">Puede declarar varios atributos individualmente, como se muestra en el ejemplo de código anterior, o bien puede declarar en un conjunto de corchetes si utiliza un punto y coma para separar los atributos individuales y los constructores, como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="024d7-131">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="024d7-132">Atributos encontrados normalmente incluyen el `Obsolete` atributos de atributo, atributos de consideraciones de seguridad, compatibilidad con COM, atributos relacionados con las que la propiedad del código y atributos que indica si se puede serializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="024d7-132">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="024d7-133">En el ejemplo siguiente se muestra el uso de la `Obsolete` atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-133">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="024d7-134">Para los destinos de atributo `assembly` y `module`, aplicar los atributos a un nivel superior `do` enlace en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="024d7-134">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="024d7-135">Puede incluir la palabra `assembly` o `module` en la declaración de atributo, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="024d7-135">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="024d7-136">Si se omite el destino del atributo para un atributo aplicado a un `do` de enlace, el compilador de F # intenta determinar el destino del atributo que tenga sentido para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-136">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="024d7-137">Muchas clases de atributos tienen un atributo de tipo `System.AttributeUsageAttribute` que incluye información sobre los posibles destinos admitidos para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="024d7-137">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="024d7-138">Si el `System.AttributeUsageAttribute` indica que el atributo admite funciones como destinos, el atributo se lleva a cabo para aplicar al punto de entrada principal del programa.</span><span class="sxs-lookup"><span data-stu-id="024d7-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="024d7-139">Si el `System.AttributeUsageAttribute` indica que el atributo admite ensamblados como destinos, el compilador usa el atributo para aplicar al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="024d7-139">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="024d7-140">Mayoría de los atributos no se aplica a las funciones y ensamblados, pero en casos donde lo hacen, se realiza el atributo al que se aplica a la función principal del programa.</span><span class="sxs-lookup"><span data-stu-id="024d7-140">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="024d7-141">Si el destino del atributo se especifica explícitamente, el atributo se aplica al destino especificado.</span><span class="sxs-lookup"><span data-stu-id="024d7-141">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="024d7-142">Aunque normalmente no es necesario especificar el atributo de destino explícitamente, los valores válidos para *destino* en un atributo se muestran en la siguiente tabla, junto con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="024d7-142">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="024d7-143">Destino del atributo</span><span class="sxs-lookup"><span data-stu-id="024d7-143">Attribute target</span></span></td>
    <th><span data-ttu-id="024d7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="024d7-144">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-145">ensamblado</span><span class="sxs-lookup"><span data-stu-id="024d7-145">assembly</span></span></td>
    <td><span data-ttu-id="024d7-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="024d7-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-147">return</span><span class="sxs-lookup"><span data-stu-id="024d7-147">return</span></span></td>
    <td><span data-ttu-id="024d7-148">' permiten function1 x: [<return: Obsolete>] int = x + 1'</span><span class="sxs-lookup"><span data-stu-id="024d7-148">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-149">campo</span><span class="sxs-lookup"><span data-stu-id="024d7-149">field</span></span></td>
    <td><span data-ttu-id="024d7-150">' [<field: DefaultValue>] x: int mutable val'</span><span class="sxs-lookup"><span data-stu-id="024d7-150">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-151">propiedad</span><span class="sxs-lookup"><span data-stu-id="024d7-151">property</span></span></td>
    <td><span data-ttu-id="024d7-152">' [<property: Obsolete>] esto. MyProperty = x'</span><span class="sxs-lookup"><span data-stu-id="024d7-152">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-153">Param</span><span class="sxs-lookup"><span data-stu-id="024d7-153">param</span></span></td>
    <td><span data-ttu-id="024d7-154">' miembro de este. MyMethod ([<param: Out>] x: ref<int>) = x: = 10'</span><span class="sxs-lookup"><span data-stu-id="024d7-154">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="024d7-155">type</span><span class="sxs-lookup"><span data-stu-id="024d7-155">type</span></span></td>
    <td><span data-ttu-id="024d7-156">
        ```
        [<type: StructLayout(Sequential)>] Escriba MyStruct = struct x: byte y: int final```
    </span><span class="sxs-lookup"><span data-stu-id="024d7-156">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="024d7-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="024d7-157">See Also</span></span>

[<span data-ttu-id="024d7-158">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="024d7-158">F# Language Reference</span></span>](index.md)
