---
description: 'Más información sobre: <Method> elemento (.net Native)'
title: <Method> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 76c379ed81e721316e4293b20ba89acfbc9d174f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747531"
---
# <a name="method-element-net-native"></a><span data-ttu-id="c96d6-103">\<Method> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c96d6-103">\<Method> Element (.NET Native)</span></span>

<span data-ttu-id="c96d6-104">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-104">Applies runtime reflection policy to a constructor or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c96d6-105">Syntax</span></span>  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c96d6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c96d6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c96d6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c96d6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c96d6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c96d6-108">Attributes</span></span>  
  
|<span data-ttu-id="c96d6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c96d6-109">Attribute</span></span>|<span data-ttu-id="c96d6-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="c96d6-110">Attribute type</span></span>|<span data-ttu-id="c96d6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="c96d6-112">General</span><span class="sxs-lookup"><span data-stu-id="c96d6-112">General</span></span>|<span data-ttu-id="c96d6-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c96d6-113">Required attribute.</span></span> <span data-ttu-id="c96d6-114">Especifica el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-114">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="c96d6-115">General</span><span class="sxs-lookup"><span data-stu-id="c96d6-115">General</span></span>|<span data-ttu-id="c96d6-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c96d6-116">Optional attribute.</span></span> <span data-ttu-id="c96d6-117">Especifica la signatura del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-117">Specifies the method signature.</span></span> <span data-ttu-id="c96d6-118">Si hay varios parámetros, se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="c96d6-118">If multiple parameters are present, they are separated by commas.</span></span> <span data-ttu-id="c96d6-119">Por ejemplo, el elemento `<Method>` siguiente define la política del método <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>.</span><span class="sxs-lookup"><span data-stu-id="c96d6-119">For example, the following `<Method>` element defines policy for the <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> method.</span></span><br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> <span data-ttu-id="c96d6-120">Si el atributo no está presente, la directiva de tiempo de ejecución se aplica a todas las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-120">If the attribute is absent, the runtime directive applies to all overloads of the method.</span></span>|  
|`Browse`|<span data-ttu-id="c96d6-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c96d6-121">Reflection</span></span>|<span data-ttu-id="c96d6-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c96d6-122">Optional attribute.</span></span> <span data-ttu-id="c96d6-123">Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c96d6-123">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c96d6-124">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c96d6-124">Reflection</span></span>|<span data-ttu-id="c96d6-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c96d6-125">Optional attribute.</span></span> <span data-ttu-id="c96d6-126">Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="c96d6-126">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="c96d6-127">Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c96d6-127">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="c96d6-128">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="c96d6-128">Name attribute</span></span>  
  
|<span data-ttu-id="c96d6-129">Value</span><span class="sxs-lookup"><span data-stu-id="c96d6-129">Value</span></span>|<span data-ttu-id="c96d6-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c96d6-131">*method_name*</span><span class="sxs-lookup"><span data-stu-id="c96d6-131">*method_name*</span></span>|<span data-ttu-id="c96d6-132">El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-132">The method name.</span></span> <span data-ttu-id="c96d6-133">El tipo del método se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c96d6-133">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="c96d6-134">Signature (atributo)</span><span class="sxs-lookup"><span data-stu-id="c96d6-134">Signature attribute</span></span>  
  
|<span data-ttu-id="c96d6-135">Value</span><span class="sxs-lookup"><span data-stu-id="c96d6-135">Value</span></span>|<span data-ttu-id="c96d6-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c96d6-137">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="c96d6-137">*method_signature*</span></span>|<span data-ttu-id="c96d6-138">Los tipos de parámetros que constituyen la signatura del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-138">The parameter types that form the method signature.</span></span> <span data-ttu-id="c96d6-139">Si hay varios parámetros, se separan por comas; por ejemplo, `"System.String,System.Int32,System.Int32)"`.</span><span class="sxs-lookup"><span data-stu-id="c96d6-139">Multiple parameters are separated by commas, for example, `"System.String,System.Int32,System.Int32)"`.</span></span> <span data-ttu-id="c96d6-140">Los nombres de tipo de parámetro deben ser completos.</span><span class="sxs-lookup"><span data-stu-id="c96d6-140">Parameter type names should be fully qualified.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="c96d6-141">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="c96d6-141">All other attributes</span></span>  
  
|<span data-ttu-id="c96d6-142">Value</span><span class="sxs-lookup"><span data-stu-id="c96d6-142">Value</span></span>|<span data-ttu-id="c96d6-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c96d6-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c96d6-144">*policy_setting*</span></span>|<span data-ttu-id="c96d6-145">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="c96d6-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="c96d6-146">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="c96d6-146">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="c96d6-147">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="c96d6-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c96d6-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c96d6-148">Child Elements</span></span>  
  
|<span data-ttu-id="c96d6-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="c96d6-149">Element</span></span>|<span data-ttu-id="c96d6-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-150">Description</span></span>|  
|-------------|-----------------|  
|[\<Parameter>](parameter-element-net-native.md)|<span data-ttu-id="c96d6-151">Aplica la directiva al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-151">Applies policy to the type of the argument passed to a method.</span></span>|  
|[\<GenericParameter>](genericparameter-element-net-native.md)|<span data-ttu-id="c96d6-152">Aplica la directiva al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="c96d6-152">Applies policy to the parameter type of a generic type or method.</span></span>|  
|[\<ImpliesType>](impliestype-element-net-native.md)|<span data-ttu-id="c96d6-153">Aplica la directiva a un tipo, si esa directiva se ha aplicado al método representado por el elemento `<Method>` contenedor.</span><span class="sxs-lookup"><span data-stu-id="c96d6-153">Applies policy to a type, if that policy has been applied to the method represented by the containing `<Method>` element.</span></span>|  
|[\<TypeParameter>](typeparameter-element-net-native.md)|<span data-ttu-id="c96d6-154">Aplica la directiva al tipo representado por un argumento <xref:System.Type> que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-154">Applies policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c96d6-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c96d6-155">Parent Elements</span></span>  
  
|<span data-ttu-id="c96d6-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="c96d6-156">Element</span></span>|<span data-ttu-id="c96d6-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96d6-157">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="c96d6-158">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c96d6-158">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="c96d6-159">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c96d6-159">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c96d6-160">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c96d6-160">Remarks</span></span>  

 <span data-ttu-id="c96d6-161">Un elemento `<Method>` de un método genérico aplica su directiva a todas las instancias que no tienen su propia directiva.</span><span class="sxs-lookup"><span data-stu-id="c96d6-161">A `<Method>` element of a generic method applies its policy to all instantiations that do not have their own policy.</span></span>  
  
 <span data-ttu-id="c96d6-162">Puede utilizar el atributo `Signature` para especificar la directiva de sobrecarga de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="c96d6-162">You can use the `Signature` attribute to specify policy for a particular method overload.</span></span> <span data-ttu-id="c96d6-163">Por otra parte, si el atributo `Signature` no está presente, la directiva de tiempo de ejecución se aplica a todas las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="c96d6-163">Otherwise, if the `Signature` attribute is absent, the runtime directive applies to all overloads of the method.</span></span>  
  
 <span data-ttu-id="c96d6-164">No se puede definir la directiva de reflexión en tiempo de ejecución para un constructor mediante el uso del elemento `<Method>`.</span><span class="sxs-lookup"><span data-stu-id="c96d6-164">You cannot define the runtime reflection policy for a constructor by using the `<Method>` element.</span></span> <span data-ttu-id="c96d6-165">En su lugar, use el `Activate` atributo del  [\<Assembly>](assembly-element-net-native.md) [\<Namespace>](namespace-element-net-native.md) elemento,, [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c96d6-165">Instead, use the `Activate` attribute of the  [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), [\<Type>](type-element-net-native.md), or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c96d6-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c96d6-166">Example</span></span>  

 <span data-ttu-id="c96d6-167">El método `Stringify` del siguiente ejemplo es un método de formato de uso general que utiliza la reflexión para convertir un objeto en su representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="c96d6-167">The `Stringify` method in the following example is a general-purpose formatting method that uses reflection to convert an object to its string representation.</span></span> <span data-ttu-id="c96d6-168">Además de llamar al método `ToString` predeterminado del objeto, el método puede generar una cadena de resultado con formato; para ello, se pasa el método `ToString` de un objeto a una cadena de formato, a una implementación de <xref:System.IFormatProvider> o a ambos.</span><span class="sxs-lookup"><span data-stu-id="c96d6-168">In addition to calling the object's default `ToString` method, the method can produce a formatted result string by passing an object's `ToString` method a format string, an <xref:System.IFormatProvider> implementation, or both.</span></span> <span data-ttu-id="c96d6-169">También puede llamar a una de las sobrecargas <xref:System.Convert.ToString%2A?displayProperty=nameWithType> que convierte un número en su representación binaria, octal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="c96d6-169">It can also call one of the <xref:System.Convert.ToString%2A?displayProperty=nameWithType> overloads that converts a number to its binary, hexadecimal, or octal representation.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="c96d6-170">El método `Stringify` puede llamarse mediante código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c96d6-170">The `Stringify` method can be called by code like the following:</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="c96d6-171">Pero cuando se compila con .NET Native, el ejemplo puede producir un número de excepciones en tiempo de ejecución, incluidas excepciones <xref:System.NullReferenceException> y [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Esto se produce porque el método `Stringify` está pensado principalmente para admitir el formato dinámico de los tipos primitivos de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c96d6-171">However, when compiled with .NET Native, the example can throw an number of exceptions at runtime, including <xref:System.NullReferenceException> and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions, This occurs because the `Stringify` method is intended primarily to support dynamically formatting the primitive types in the .NET Framework Class Library.</span></span> <span data-ttu-id="c96d6-172">No obstante, sus metadatos no están disponibles en el archivo de directivas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c96d6-172">However, their metadata is not made available by the default directives file.</span></span> <span data-ttu-id="c96d6-173">Incluso cuando sus metadatos están disponibles, el ejemplo genera excepciones [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) porque las implementaciones `ToString` adecuadas no se han incluido en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="c96d6-173">Even when their metadata is made available, however, the example throws [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions because the appropriate `ToString` implementations have not been include in the native code.</span></span>  
  
 <span data-ttu-id="c96d6-174">Estas excepciones se pueden eliminar mediante el [\<Type>](type-element-net-native.md) elemento para definir los tipos cuyos metadatos deben estar presentes y agregar `<Method>` elementos para asegurarse de que la implementación de sobrecargas de método que se pueden llamar dinámicamente también está presente.</span><span class="sxs-lookup"><span data-stu-id="c96d6-174">These exceptions can all be eliminated by using the [\<Type>](type-element-net-native.md) element to define the types whose metadata must be present, and by adding `<Method>` elements to ensure that the implementation of method overloads that can be called dynamically is also present.</span></span> <span data-ttu-id="c96d6-175">El siguiente es el archivo default.rd.xml que elimina estas excepciones y permite que el ejemplo se ejecute sin errores.</span><span class="sxs-lookup"><span data-stu-id="c96d6-175">The following is the default.rd.xml file that eliminates these exceptions and allows the example to execute without error.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c96d6-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="c96d6-176">See also</span></span>

- [<span data-ttu-id="c96d6-177">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c96d6-177">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c96d6-178">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c96d6-178">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c96d6-179">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c96d6-179">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="c96d6-180">Elemento \<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="c96d6-180">\<MethodInstantiation> Element</span></span>](methodinstantiation-element-net-native.md)
