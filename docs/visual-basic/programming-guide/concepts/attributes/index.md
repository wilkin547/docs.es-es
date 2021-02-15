---
description: 'Más información sobre: información general sobre los atributos (Visual Basic)'
title: Información general de atributos
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: f25e69452f0af1c89af667619e673f8906704d1f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100437727"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="c0fd3-103">Información general sobre los atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0fd3-103">Attributes overview (Visual Basic)</span></span>

<span data-ttu-id="c0fd3-104">Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-104">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="c0fd3-105">Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-105">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="c0fd3-106">Para más información, vea [Reflexión (Visual Basic)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-106">For more information, see [Reflection (Visual Basic)](../reflection.md).</span></span>

<span data-ttu-id="c0fd3-107">Los atributos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-107">Attributes have the following properties:</span></span>

- <span data-ttu-id="c0fd3-108">Los atributos agregan metadatos al programa.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-108">Attributes add metadata to your program.</span></span> <span data-ttu-id="c0fd3-109">Los *metadatos* son información sobre los tipos definidos en un programa.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-109">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="c0fd3-110">Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-110">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="c0fd3-111">Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-111">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="c0fd3-112">Para más información, vea [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-112">For more information, see, [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md).</span></span>

- <span data-ttu-id="c0fd3-113">Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-113">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>

- <span data-ttu-id="c0fd3-114">Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-114">Attributes can accept arguments in the same way as methods and properties.</span></span>

- <span data-ttu-id="c0fd3-115">El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-115">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="c0fd3-116">Para más información, vea [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-116">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="c0fd3-117">Utilizar atributos</span><span class="sxs-lookup"><span data-stu-id="c0fd3-117">Using Attributes</span></span>

<span data-ttu-id="c0fd3-118">Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-118">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="c0fd3-119">En Visual Basic, un atributo está entre corchetes angulares ( \< > ).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-119">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="c0fd3-120">Debe aparecer inmediatamente antes del elemento al que se aplica, en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-120">It must appear immediately before the element to which it is applied, on the same line.</span></span>

<span data-ttu-id="c0fd3-121">En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-121">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 <span data-ttu-id="c0fd3-122">Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara de esta forma:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-122">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

<span data-ttu-id="c0fd3-123">En una declaración se puede colocar más de un atributo:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-123">More than one attribute can be placed on a declaration:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

<span data-ttu-id="c0fd3-124">Algunos atributos se pueden especificar más de una vez para una entidad determinada.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-124">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="c0fd3-125">Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-125">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> <span data-ttu-id="c0fd3-126">Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-126">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="c0fd3-127">Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-127">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="c0fd3-128">Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre del atributo real en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-128">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="c0fd3-129">Parámetros de atributo</span><span class="sxs-lookup"><span data-stu-id="c0fd3-129">Attribute Parameters</span></span>

<span data-ttu-id="c0fd3-130">Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-130">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="c0fd3-131">Los parámetros posicionales deben especificarse en un determinado orden y no se pueden omitir; los parámetros con nombre son opcionales y se pueden especificar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-131">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="c0fd3-132">Los parámetros posicionales se especifican en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-132">Positional parameters are specified first.</span></span> <span data-ttu-id="c0fd3-133">Por ejemplo, estos tres atributos son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-133">For example, these three attributes are equivalent:</span></span>

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

<span data-ttu-id="c0fd3-134">El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-134">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="c0fd3-135">En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-135">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="c0fd3-136">Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-136">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="c0fd3-137">Destinos de atributo</span><span class="sxs-lookup"><span data-stu-id="c0fd3-137">Attribute Targets</span></span>

<span data-ttu-id="c0fd3-138">El *destino* de un atributo es la entidad a la que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-138">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="c0fd3-139">Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-139">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="c0fd3-140">De forma predeterminada, el atributo se aplica al elemento que lo precede.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-140">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="c0fd3-141">Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-141">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="c0fd3-142">Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-142">To explicitly identify an attribute target, use the following syntax:</span></span>

```vb
<target : attribute-list>
```

<span data-ttu-id="c0fd3-143">La lista de posibles valores `target` se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-143">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="c0fd3-144">Valor del objetivo</span><span class="sxs-lookup"><span data-stu-id="c0fd3-144">Target value</span></span>|<span data-ttu-id="c0fd3-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="c0fd3-145">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="c0fd3-146">Ensamblado completo</span><span class="sxs-lookup"><span data-stu-id="c0fd3-146">Entire assembly</span></span>|
|`module`|<span data-ttu-id="c0fd3-147">Módulo del ensamblado actual (que es diferente de un módulo de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0fd3-147">Current assembly module (which is different from a Visual Basic Module)</span></span>|

 <span data-ttu-id="c0fd3-148">En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-148">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="c0fd3-149">Para más información, vea [Atributos comunes (Visual Basic)](common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c0fd3-149">For more information, see [Common Attributes (Visual Basic)](common-attributes.md).</span></span>

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a><span data-ttu-id="c0fd3-150">Usos comunes de los atributos</span><span class="sxs-lookup"><span data-stu-id="c0fd3-150">Common Uses for Attributes</span></span>

<span data-ttu-id="c0fd3-151">La lista siguiente incluye algunos de los usos comunes de atributos en el código:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-151">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="c0fd3-152">Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-152">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="c0fd3-153">Para obtener más información, vea <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-153">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>

- <span data-ttu-id="c0fd3-154">Describir cómo serializar parámetros de método al interoperar con código nativo.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-154">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="c0fd3-155">Para obtener más información, vea <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-155">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

- <span data-ttu-id="c0fd3-156">Describir las propiedades COM para clases, métodos e interfaces.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-156">Describing the COM properties for classes, methods, and interfaces.</span></span>

- <span data-ttu-id="c0fd3-157">Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-157">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>

- <span data-ttu-id="c0fd3-158">Describir los ensamblados en cuanto a título, versión, descripción o marca.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-158">Describing your assembly in terms of title, version, description, or trademark.</span></span>

- <span data-ttu-id="c0fd3-159">Describir qué miembros de una clase serializar para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-159">Describing which members of a class to serialize for persistence.</span></span>

- <span data-ttu-id="c0fd3-160">Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-160">Describing how to map between class members and XML nodes for XML serialization.</span></span>

- <span data-ttu-id="c0fd3-161">Describir los requisitos de seguridad para los métodos.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-161">Describing the security requirements for methods.</span></span>

- <span data-ttu-id="c0fd3-162">Especificar las características utilizadas para reforzar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-162">Specifying characteristics used to enforce security.</span></span>

- <span data-ttu-id="c0fd3-163">Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-163">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>

- <span data-ttu-id="c0fd3-164">Obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="c0fd3-164">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c0fd3-165">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c0fd3-165">Related Sections</span></span>

<span data-ttu-id="c0fd3-166">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c0fd3-166">For more information, see:</span></span>

- <span data-ttu-id="c0fd3-167">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c0fd3-167">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md)</span></span>

- <span data-ttu-id="c0fd3-168">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c0fd3-168">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>

- <span data-ttu-id="c0fd3-169">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](how-to-create-a-c-cpp-union-by-using-attributes.md) (Creación de uniones de C/C++ mediante la utilización de atributos [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c0fd3-169">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](how-to-create-a-c-cpp-union-by-using-attributes.md)</span></span>

- <span data-ttu-id="c0fd3-170">[Common Attributes (Visual Basic)](common-attributes.md) (Atributos comunes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c0fd3-170">[Common Attributes (Visual Basic)](common-attributes.md)</span></span>

- [<span data-ttu-id="c0fd3-171">Información del llamador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0fd3-171">Caller Information (Visual Basic)</span></span>](../caller-information.md)

## <a name="see-also"></a><span data-ttu-id="c0fd3-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0fd3-172">See also</span></span>

- [<span data-ttu-id="c0fd3-173">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0fd3-173">Visual Basic Programming Guide</span></span>](../../index.md)
- <span data-ttu-id="c0fd3-174">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c0fd3-174">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="c0fd3-175">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0fd3-175">Attributes</span></span>](../../../../standard/attributes/index.md)
