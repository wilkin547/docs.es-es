---
title: Información general sobre los atributos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: bb012b49c76963306d723d7732b4c7054bf13ebb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827697"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="bb3b8-102">Información general sobre los atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb3b8-102">Attributes overview (Visual Basic)</span></span>
<span data-ttu-id="bb3b8-103">Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="bb3b8-104">Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="bb3b8-105">Para más información, vea [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-105">For more information, see [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="bb3b8-106">Los atributos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="bb3b8-107">Los atributos agregan metadatos al programa.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="bb3b8-108">Los *metadatos* son información sobre los tipos definidos en un programa.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="bb3b8-109">Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="bb3b8-110">Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="bb3b8-111">Para más información, vea [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-111">For more information, see, [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="bb3b8-112">Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="bb3b8-113">Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="bb3b8-114">El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="bb3b8-115">Para más información, vea [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="bb3b8-116">Utilizar atributos</span><span class="sxs-lookup"><span data-stu-id="bb3b8-116">Using Attributes</span></span>  
 <span data-ttu-id="bb3b8-117">Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="bb3b8-118">En Visual Basic, un atributo se encierra entre corchetes angulares (\< >).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="bb3b8-119">Debe aparecer inmediatamente antes del elemento al que se aplica, en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>  
  
 <span data-ttu-id="bb3b8-120">En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```vb  
<System.Serializable()> Public Class SampleClass  
    ' Objects of this type can be serialized.  
End Class  
```  
  
 <span data-ttu-id="bb3b8-121">Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara de esta forma:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
<System.Runtime.InteropServices.DllImport("user32.dll")>   
Sub SampleMethod()  
End Sub  
```  
  
 <span data-ttu-id="bb3b8-122">En una declaración se puede colocar más de un atributo:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-122">More than one attribute can be placed on a declaration:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
Sub MethodA(<[In](), Out()> ByVal x As Double)  
End Sub  
Sub MethodB(<Out(), [In]()> ByVal x As Double)  
End Sub  
```  
  
 <span data-ttu-id="bb3b8-123">Algunos atributos se pueden especificar más de una vez para una entidad determinada.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="bb3b8-124">Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```vb  
<Conditional("DEBUG"), Conditional("TEST1")>   
Sub TraceMethod()  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="bb3b8-125">Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="bb3b8-126">Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="bb3b8-127">Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre del atributo real en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="bb3b8-128">Parámetros de atributo</span><span class="sxs-lookup"><span data-stu-id="bb3b8-128">Attribute Parameters</span></span>  
 <span data-ttu-id="bb3b8-129">Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="bb3b8-130">Los parámetros posicionales deben especificarse en un determinado orden y no se pueden omitir; los parámetros con nombre son opcionales y se pueden especificar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="bb3b8-131">Los parámetros posicionales se especifican en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-131">Positional parameters are specified first.</span></span> <span data-ttu-id="bb3b8-132">Por ejemplo, estos tres atributos son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-132">For example, these three attributes are equivalent:</span></span>  
  
```vb  
<DllImport("user32.dll")>  
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>  
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>  
```  
  
 <span data-ttu-id="bb3b8-133">El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="bb3b8-134">En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="bb3b8-135">Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="bb3b8-136">Destinos de atributo</span><span class="sxs-lookup"><span data-stu-id="bb3b8-136">Attribute Targets</span></span>  
 <span data-ttu-id="bb3b8-137">El *destino* de un atributo es la entidad a la que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="bb3b8-138">Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="bb3b8-139">De forma predeterminada, el atributo se aplica al elemento que lo precede.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="bb3b8-140">Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="bb3b8-141">Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-141">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```vb  
<target : attribute-list>  
```  
  
 <span data-ttu-id="bb3b8-142">La lista de posibles valores `target` se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-142">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="bb3b8-143">Valor del objetivo</span><span class="sxs-lookup"><span data-stu-id="bb3b8-143">Target value</span></span>|<span data-ttu-id="bb3b8-144">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bb3b8-144">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="bb3b8-145">Ensamblado completo</span><span class="sxs-lookup"><span data-stu-id="bb3b8-145">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="bb3b8-146">Módulo del ensamblado actual (que es diferente de un módulo de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb3b8-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|  
  
 <span data-ttu-id="bb3b8-147">En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="bb3b8-148">Para más información, vea [Atributos comunes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bb3b8-148">For more information, see [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```vb  
Imports System.Reflection  
<Assembly: AssemblyTitleAttribute("Production assembly 4"),   
Module: CLSCompliant(True)>   
```  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="bb3b8-149">Usos comunes de los atributos</span><span class="sxs-lookup"><span data-stu-id="bb3b8-149">Common Uses for Attributes</span></span>  
 <span data-ttu-id="bb3b8-150">La lista siguiente incluye algunos de los usos comunes de atributos en el código:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-150">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="bb3b8-151">Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="bb3b8-152">Para obtener más información, consulta <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="bb3b8-153">Describir cómo serializar parámetros de método al interoperar con código nativo.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="bb3b8-154">Para obtener más información, consulta <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="bb3b8-155">Describir las propiedades COM para clases, métodos e interfaces.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-155">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="bb3b8-156">Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="bb3b8-157">Describir los ensamblados en cuanto a título, versión, descripción o marca.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="bb3b8-158">Describir qué miembros de una clase serializar para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-158">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="bb3b8-159">Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="bb3b8-160">Describir los requisitos de seguridad para los métodos.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-160">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="bb3b8-161">Especificar las características utilizadas para reforzar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-161">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="bb3b8-162">Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="bb3b8-163">Obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="bb3b8-163">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb3b8-164">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bb3b8-164">Related Sections</span></span>  
 <span data-ttu-id="bb3b8-165">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="bb3b8-165">For more information, see:</span></span>  
  
-   <span data-ttu-id="bb3b8-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="bb3b8-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>  
  
-   <span data-ttu-id="bb3b8-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="bb3b8-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>  
  
-   [<span data-ttu-id="bb3b8-168">Cómo: Crear una unión de C/c ++ mediante atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb3b8-168">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   <span data-ttu-id="bb3b8-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Atributos comunes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="bb3b8-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)</span></span>  
  
-   [<span data-ttu-id="bb3b8-170">Información del llamador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb3b8-170">Caller Information (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb3b8-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb3b8-171">See also</span></span>

- [<span data-ttu-id="bb3b8-172">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb3b8-172">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="bb3b8-173">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb3b8-173">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="bb3b8-174">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb3b8-174">Attributes</span></span>](../../../../standard/attributes/index.md)
