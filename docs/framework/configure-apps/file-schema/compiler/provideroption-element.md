---
title: <providerOption> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155406"
---
# <a name="provideroption-element"></a><span data-ttu-id="d8142-102">\<providerOption> Element</span><span class="sxs-lookup"><span data-stu-id="d8142-102">\<providerOption> Element</span></span>
<span data-ttu-id="d8142-103">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d8142-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="d8142-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8142-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d8142-105">&nbsp;&nbsp;[**\<>system.codedom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8142-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="d8142-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiladores>**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8142-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="d8142-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del compilador**](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8142-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="d8142-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span><span class="sxs-lookup"><span data-stu-id="d8142-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d8142-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8142-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8142-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d8142-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8142-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d8142-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8142-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8142-112">Attributes</span></span>  
  
|<span data-ttu-id="d8142-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d8142-113">Attribute</span></span>|<span data-ttu-id="d8142-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8142-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d8142-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d8142-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="d8142-116">Especifica el nombre de la opción; por ejemplo, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="d8142-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="d8142-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d8142-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="d8142-118">Especifica el valor de la opción; por ejemplo, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="d8142-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8142-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d8142-119">Child Elements</span></span>  
 <span data-ttu-id="d8142-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d8142-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8142-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d8142-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d8142-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8142-122">Element</span></span>|<span data-ttu-id="d8142-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8142-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8142-124">\<configuración> Elemento</span><span class="sxs-lookup"><span data-stu-id="d8142-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="d8142-125">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8142-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="d8142-126">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="d8142-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="d8142-127">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="d8142-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="d8142-128">\<compiladores> Element</span><span class="sxs-lookup"><span data-stu-id="d8142-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="d8142-129">Contenedor para elementos de configuración del compilador; contiene cero `<compiler>` o más elementos.</span><span class="sxs-lookup"><span data-stu-id="d8142-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="d8142-130">\<compilador> elemento</span><span class="sxs-lookup"><span data-stu-id="d8142-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="d8142-131">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d8142-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8142-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8142-132">Remarks</span></span>  
 <span data-ttu-id="d8142-133">En la versión 3.5 de .NET Framework, los proveedores de código del `<providerOption>` modelo de objetos de documento de código (CodeDOM) pueden admitir opciones específicas del proveedor mediante el elemento.</span><span class="sxs-lookup"><span data-stu-id="d8142-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="d8142-134">.NET Framework 3.5 incluye ensamblados actualizados de .NET Framework 2.0 y proporciona nuevos ensamblados de la versión 3.5 que contienen nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="d8142-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="d8142-135">Los proveedores de código de Microsoft C y Visual Basic están contenidos en ensamblados de .NET Framework 2.0, pero se han actualizado para admitir compiladores de la versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="d8142-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="d8142-136">De forma predeterminada, los proveedores de código actualizados generan código para los compiladores de la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="d8142-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="d8142-137">Puede usar `<providerOption>` el elemento para cambiar la versión del compilador de destino a 3.5.</span><span class="sxs-lookup"><span data-stu-id="d8142-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="d8142-138">Para ello, especifique "CompilerVersion" `name` para el atributo y "v3.5" para el `value` atributo.</span><span class="sxs-lookup"><span data-stu-id="d8142-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="d8142-139">Debe preceder el número de versión con una "v" en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d8142-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="d8142-140">Puede hacer que la especificación `<providerOption>` de versión sea global agregando el elemento al archivo Machine.config o Web.config raíz de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="d8142-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="d8142-141">Si actualiza la versión predeterminada del compilador a 3.5 en el archivo Machine.config, puede volver `<providerOption>` a cambiarla a 2.0 por aplicación mediante el elemento del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8142-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="d8142-142">Los implementadores de proveedores de código CodeDOM `providerOptions` pueden procesar <xref:System.Collections.Generic.IDictionary%602>opciones personalizadas proporcionando un constructor que toma un parámetro de tipo .</span><span class="sxs-lookup"><span data-stu-id="d8142-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8142-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8142-143">Example</span></span>  
 <span data-ttu-id="d8142-144">En el ejemplo siguiente se muestra cómo especificar que se debe usar la versión 3.5 del proveedor de código de C.</span><span class="sxs-lookup"><span data-stu-id="d8142-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8142-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8142-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="d8142-146">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d8142-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d8142-147">\<compiladores> Element</span><span class="sxs-lookup"><span data-stu-id="d8142-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="d8142-148">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="d8142-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="d8142-149">[Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d8142-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
