---
title: Atributos (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f9fc23cf7afbd28f0c9ae438cbce298cbf362fbd
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="attributes-c"></a><span data-ttu-id="c1926-102">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-102">Attributes (C#)</span></span>
<span data-ttu-id="c1926-103">Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.).</span><span class="sxs-lookup"><span data-stu-id="c1926-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="c1926-104">Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*.</span><span class="sxs-lookup"><span data-stu-id="c1926-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="c1926-105">Para obtener más información, vea [Reflexión (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="c1926-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="c1926-106">Los atributos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1926-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="c1926-107">Los atributos agregan metadatos al programa.</span><span class="sxs-lookup"><span data-stu-id="c1926-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="c1926-108">Los *metadatos* son información sobre los tipos definidos en un programa.</span><span class="sxs-lookup"><span data-stu-id="c1926-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="c1926-109">Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1926-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="c1926-110">Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="c1926-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="c1926-111">Para obtener más información, vea [Crear atributos personalizados (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c1926-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="c1926-112">Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.</span><span class="sxs-lookup"><span data-stu-id="c1926-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="c1926-113">Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c1926-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="c1926-114">El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="c1926-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="c1926-115">Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="c1926-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="c1926-116">Utilizar atributos</span><span class="sxs-lookup"><span data-stu-id="c1926-116">Using Attributes</span></span>  
 <span data-ttu-id="c1926-117">Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido.</span><span class="sxs-lookup"><span data-stu-id="c1926-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="c1926-118">En C#, se especifica un atributo al colocar el nombre del atributo, encerrado entre corchetes ([]), encima de la declaración de la entidad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="c1926-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="c1926-119">En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:</span><span class="sxs-lookup"><span data-stu-id="c1926-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="c1926-120">Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara de esta forma:</span><span class="sxs-lookup"><span data-stu-id="c1926-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="c1926-121">En una declaración se puede colocar más de un atributo:</span><span class="sxs-lookup"><span data-stu-id="c1926-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="c1926-122">Algunos atributos se pueden especificar más de una vez para una entidad determinada.</span><span class="sxs-lookup"><span data-stu-id="c1926-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="c1926-123">Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="c1926-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="c1926-124">Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1926-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="c1926-125">Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="c1926-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="c1926-126">Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre del atributo real en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1926-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="c1926-127">Parámetros de atributo</span><span class="sxs-lookup"><span data-stu-id="c1926-127">Attribute Parameters</span></span>  
 <span data-ttu-id="c1926-128">Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre.</span><span class="sxs-lookup"><span data-stu-id="c1926-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="c1926-129">Los parámetros posicionales deben especificarse en un determinado orden y no se pueden omitir; los parámetros con nombre son opcionales y se pueden especificar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="c1926-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="c1926-130">Los parámetros posicionales se especifican en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c1926-130">Positional parameters are specified first.</span></span> <span data-ttu-id="c1926-131">Por ejemplo, estos tres atributos son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c1926-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="c1926-132">El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre.</span><span class="sxs-lookup"><span data-stu-id="c1926-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="c1926-133">En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="c1926-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="c1926-134">Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c1926-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="c1926-135">Destinos de atributo</span><span class="sxs-lookup"><span data-stu-id="c1926-135">Attribute Targets</span></span>  
 <span data-ttu-id="c1926-136">El *destino* de un atributo es la entidad a la que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="c1926-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="c1926-137">Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="c1926-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="c1926-138">De forma predeterminada, el atributo se aplica al elemento que lo precede.</span><span class="sxs-lookup"><span data-stu-id="c1926-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="c1926-139">Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c1926-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="c1926-140">Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1926-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="c1926-141">La lista de posibles valores `target` se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c1926-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="c1926-142">Valor del objetivo</span><span class="sxs-lookup"><span data-stu-id="c1926-142">Target value</span></span>|<span data-ttu-id="c1926-143">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="c1926-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="c1926-144">Ensamblado completo</span><span class="sxs-lookup"><span data-stu-id="c1926-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="c1926-145">Módulo de ensamblado actual</span><span class="sxs-lookup"><span data-stu-id="c1926-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="c1926-146">Campo de una clase o un struct</span><span class="sxs-lookup"><span data-stu-id="c1926-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="c1926-147">Evento</span><span class="sxs-lookup"><span data-stu-id="c1926-147">Event</span></span>|  
|`method`|<span data-ttu-id="c1926-148">Método o descriptores de acceso de propiedad `get` y `set`</span><span class="sxs-lookup"><span data-stu-id="c1926-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="c1926-149">Parámetros de método o parámetros de descriptor de acceso de propiedad `set`</span><span class="sxs-lookup"><span data-stu-id="c1926-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="c1926-150">Propiedad</span><span class="sxs-lookup"><span data-stu-id="c1926-150">Property</span></span>|  
|`return`|<span data-ttu-id="c1926-151">Valor devuelto de un método, indexador de propiedad o descriptor de acceso de propiedad `get`</span><span class="sxs-lookup"><span data-stu-id="c1926-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="c1926-152">Estructura, clase, interfaz, enumeración o delegado</span><span class="sxs-lookup"><span data-stu-id="c1926-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="c1926-153">En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos.</span><span class="sxs-lookup"><span data-stu-id="c1926-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="c1926-154">Para obtener más información, vea [Atributos comunes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c1926-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="c1926-155">En el ejemplo siguiente, se muestra cómo aplicar atributos a métodos, parámetros de método y valores devueltos por métodos en C#.</span><span class="sxs-lookup"><span data-stu-id="c1926-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="c1926-156">Independientemente de los destinos en los que `SomeAttr` se define para que sea válido, debe especificarse el destino `return`, incluso si `SomeAttr` se ha definido para que se aplique solo a los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="c1926-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="c1926-157">En otras palabras, el compilador no usará información de `AttributeUsage` para resolver destinos de atributo ambiguos.</span><span class="sxs-lookup"><span data-stu-id="c1926-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="c1926-158">Para obtener más información, consulte [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="c1926-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="c1926-159">Usos comunes de los atributos</span><span class="sxs-lookup"><span data-stu-id="c1926-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="c1926-160">La lista siguiente incluye algunos de los usos comunes de atributos en el código:</span><span class="sxs-lookup"><span data-stu-id="c1926-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="c1926-161">Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP.</span><span class="sxs-lookup"><span data-stu-id="c1926-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="c1926-162">Para obtener más información, consulta <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c1926-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="c1926-163">Describir cómo serializar parámetros de método al interoperar con código nativo.</span><span class="sxs-lookup"><span data-stu-id="c1926-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="c1926-164">Para obtener más información, consulta <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c1926-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="c1926-165">Describir las propiedades COM para clases, métodos e interfaces.</span><span class="sxs-lookup"><span data-stu-id="c1926-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="c1926-166">Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c1926-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="c1926-167">Describir los ensamblados en cuanto a título, versión, descripción o marca.</span><span class="sxs-lookup"><span data-stu-id="c1926-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="c1926-168">Describir qué miembros de una clase serializar para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="c1926-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="c1926-169">Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="c1926-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="c1926-170">Describir los requisitos de seguridad para los métodos.</span><span class="sxs-lookup"><span data-stu-id="c1926-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="c1926-171">Especificar las características utilizadas para reforzar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c1926-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="c1926-172">Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.</span><span class="sxs-lookup"><span data-stu-id="c1926-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="c1926-173">Obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="c1926-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c1926-174">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c1926-174">Related Sections</span></span>  
 <span data-ttu-id="c1926-175">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c1926-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="c1926-176">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="c1926-177">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-177">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="c1926-178">Cómo: Crear una unión de C/C++ mediante atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="c1926-179">Atributos comunes (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="c1926-180">Información del llamador (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-180">Caller Information (C#)</span></span>](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1926-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1926-181">See Also</span></span>  
 [<span data-ttu-id="c1926-182">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c1926-182">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c1926-183">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="c1926-183">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="c1926-184">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1926-184">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)
