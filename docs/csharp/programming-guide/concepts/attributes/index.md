---
title: Atributos (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 0379bb76cf18ff836bd14aafb9cb97c30aee8ec7
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645482"
---
# <a name="attributes-c"></a><span data-ttu-id="b5e92-102">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-102">Attributes (C#)</span></span>

<span data-ttu-id="b5e92-103">Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.).</span><span class="sxs-lookup"><span data-stu-id="b5e92-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="b5e92-104">Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*.</span><span class="sxs-lookup"><span data-stu-id="b5e92-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="b5e92-105">Para obtener más información, vea [Reflexión (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-105">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="b5e92-106">Los atributos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5e92-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="b5e92-107">Los atributos agregan metadatos al programa.</span><span class="sxs-lookup"><span data-stu-id="b5e92-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="b5e92-108">Los *metadatos* son información sobre los tipos definidos en un programa.</span><span class="sxs-lookup"><span data-stu-id="b5e92-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="b5e92-109">Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b5e92-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="b5e92-110">Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="b5e92-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="b5e92-111">Para obtener más información, vea [Crear atributos personalizados (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-111">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="b5e92-112">Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.</span><span class="sxs-lookup"><span data-stu-id="b5e92-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="b5e92-113">Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b5e92-113">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="b5e92-114">El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="b5e92-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="b5e92-115">Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-115">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="b5e92-116">Uso de atributos</span><span class="sxs-lookup"><span data-stu-id="b5e92-116">Using attributes</span></span>

<span data-ttu-id="b5e92-117">Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido.</span><span class="sxs-lookup"><span data-stu-id="b5e92-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="b5e92-118">En C#, para especificar un atributo se coloca su nombre entre corchetes ([]) por encima de la declaración de la entidad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="b5e92-118">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="b5e92-119">En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:</span><span class="sxs-lookup"><span data-stu-id="b5e92-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="b5e92-120">Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5e92-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="b5e92-121">En una declaración se puede colocar más de un atributo, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5e92-121">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="b5e92-122">Algunos atributos se pueden especificar más de una vez para una entidad determinada.</span><span class="sxs-lookup"><span data-stu-id="b5e92-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="b5e92-123">Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="b5e92-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="b5e92-124">Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de las bibliotecas de .NET.</span><span class="sxs-lookup"><span data-stu-id="b5e92-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="b5e92-125">Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="b5e92-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="b5e92-126">Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre real del atributo en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5e92-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="b5e92-127">Parámetros de atributo</span><span class="sxs-lookup"><span data-stu-id="b5e92-127">Attribute parameters</span></span>

<span data-ttu-id="b5e92-128">Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre.</span><span class="sxs-lookup"><span data-stu-id="b5e92-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="b5e92-129">Los parámetros posicionales deben especificarse en un orden determinado y no se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="b5e92-129">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="b5e92-130">Los parámetros con nombre son opcionales y pueden especificarse en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="b5e92-130">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="b5e92-131">Los parámetros posicionales se especifican en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="b5e92-131">Positional parameters are specified first.</span></span> <span data-ttu-id="b5e92-132">Por ejemplo, estos tres atributos son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="b5e92-132">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="b5e92-133">El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre.</span><span class="sxs-lookup"><span data-stu-id="b5e92-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="b5e92-134">En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="b5e92-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="b5e92-135">Los parámetros posicionales corresponden a los parámetros del constructor de atributos.</span><span class="sxs-lookup"><span data-stu-id="b5e92-135">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="b5e92-136">Los parámetros con nombre u opcionales corresponden a propiedades o campos del atributo.</span><span class="sxs-lookup"><span data-stu-id="b5e92-136">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="b5e92-137">Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b5e92-137">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="b5e92-138">Destinos de atributo</span><span class="sxs-lookup"><span data-stu-id="b5e92-138">Attribute targets</span></span>

<span data-ttu-id="b5e92-139">El *destino* de un atributo es la entidad a la que se aplica dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="b5e92-139">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="b5e92-140">Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="b5e92-140">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="b5e92-141">De forma predeterminada, el atributo se aplica al elemento que sigue.</span><span class="sxs-lookup"><span data-stu-id="b5e92-141">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="b5e92-142">Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b5e92-142">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="b5e92-143">Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5e92-143">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="b5e92-144">La lista de posibles valores `target` se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5e92-144">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="b5e92-145">Valor del objetivo</span><span class="sxs-lookup"><span data-stu-id="b5e92-145">Target value</span></span>|<span data-ttu-id="b5e92-146">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="b5e92-146">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="b5e92-147">Ensamblado completo</span><span class="sxs-lookup"><span data-stu-id="b5e92-147">Entire assembly</span></span>|
|`module`|<span data-ttu-id="b5e92-148">Módulo de ensamblado actual</span><span class="sxs-lookup"><span data-stu-id="b5e92-148">Current assembly module</span></span>|
|`field`|<span data-ttu-id="b5e92-149">Campo de una clase o un struct</span><span class="sxs-lookup"><span data-stu-id="b5e92-149">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="b5e92-150">evento</span><span class="sxs-lookup"><span data-stu-id="b5e92-150">Event</span></span>|
|`method`|<span data-ttu-id="b5e92-151">Método o descriptores de acceso de propiedad `get` y `set`</span><span class="sxs-lookup"><span data-stu-id="b5e92-151">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="b5e92-152">Parámetros de método o parámetros de descriptor de acceso de propiedad `set`</span><span class="sxs-lookup"><span data-stu-id="b5e92-152">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="b5e92-153">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="b5e92-153">Property</span></span>|
|`return`|<span data-ttu-id="b5e92-154">Valor devuelto de un método, indexador de propiedad o descriptor de acceso de propiedad `get`</span><span class="sxs-lookup"><span data-stu-id="b5e92-154">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="b5e92-155">Estructura, clase, interfaz, enumeración o delegado</span><span class="sxs-lookup"><span data-stu-id="b5e92-155">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="b5e92-156">Debe especificar el valor de destino `field` para aplicar un atributo al campo de respaldo creado para una [propiedad implementada automáticamente](../../../properties.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-156">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="b5e92-157">En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos.</span><span class="sxs-lookup"><span data-stu-id="b5e92-157">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="b5e92-158">Para obtener más información, vea [Atributos comunes (C#)](../../../language-reference/attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-158">For more information, see [Common Attributes (C#)](../../../language-reference/attributes/global.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="b5e92-159">En el ejemplo siguiente, se muestra cómo aplicar atributos a métodos, parámetros de método y valores devueltos por métodos en C#.</span><span class="sxs-lookup"><span data-stu-id="b5e92-159">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="b5e92-160">Independientemente de los destinos en los que `ValidatedContract` se define para que sea válido, debe especificarse el destino `return`, incluso si `ValidatedContract` se ha definido para que se aplique solo a los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="b5e92-160">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="b5e92-161">En otras palabras, el compilador no usará información de `AttributeUsage` para resolver destinos de atributo ambiguos.</span><span class="sxs-lookup"><span data-stu-id="b5e92-161">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="b5e92-162">Para obtener más información, consulte [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span><span class="sxs-lookup"><span data-stu-id="b5e92-162">For more information, see [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="b5e92-163">Usos comunes de los atributos</span><span class="sxs-lookup"><span data-stu-id="b5e92-163">Common uses for attributes</span></span>

<span data-ttu-id="b5e92-164">La lista siguiente incluye algunos de los usos comunes de atributos en el código:</span><span class="sxs-lookup"><span data-stu-id="b5e92-164">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="b5e92-165">Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP.</span><span class="sxs-lookup"><span data-stu-id="b5e92-165">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="b5e92-166">Para obtener más información, vea <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5e92-166">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="b5e92-167">Describir cómo serializar parámetros de método al interoperar con código nativo.</span><span class="sxs-lookup"><span data-stu-id="b5e92-167">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="b5e92-168">Para obtener más información, vea <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5e92-168">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="b5e92-169">Describir las propiedades COM para clases, métodos e interfaces.</span><span class="sxs-lookup"><span data-stu-id="b5e92-169">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="b5e92-170">Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5e92-170">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="b5e92-171">Describir los ensamblados en cuanto a título, versión, descripción o marca.</span><span class="sxs-lookup"><span data-stu-id="b5e92-171">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="b5e92-172">Describir qué miembros de una clase serializar para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="b5e92-172">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="b5e92-173">Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="b5e92-173">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="b5e92-174">Describir los requisitos de seguridad para los métodos.</span><span class="sxs-lookup"><span data-stu-id="b5e92-174">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="b5e92-175">Especificar las características utilizadas para reforzar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5e92-175">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="b5e92-176">Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.</span><span class="sxs-lookup"><span data-stu-id="b5e92-176">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="b5e92-177">Obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="b5e92-177">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b5e92-178">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b5e92-178">Related sections</span></span>

<span data-ttu-id="b5e92-179">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="b5e92-179">For more information, see:</span></span>

- [<span data-ttu-id="b5e92-180">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-180">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- [<span data-ttu-id="b5e92-181">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-181">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)  
- [<span data-ttu-id="b5e92-182">Procedimiento para: Crear una unión de C/C++ mediante atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-182">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="b5e92-183">Atributos comunes (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-183">Common Attributes (C#)</span></span>](../../../language-reference/attributes/global.md)  
- [<span data-ttu-id="b5e92-184">Información del llamador (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-184">Caller Information (C#)</span></span>](../../../language-reference/attributes/caller-information.md)  

## <a name="see-also"></a><span data-ttu-id="b5e92-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5e92-185">See also</span></span>

- [<span data-ttu-id="b5e92-186">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b5e92-186">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="b5e92-187">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="b5e92-187">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="b5e92-188">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5e92-188">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="b5e92-189">Uso de atributos en C#</span><span class="sxs-lookup"><span data-stu-id="b5e92-189">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
