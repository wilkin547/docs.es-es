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
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088670"
---
# <a name="provideroption-element"></a><span data-ttu-id="04f8d-102">\<elemento > providerOption</span><span class="sxs-lookup"><span data-stu-id="04f8d-102">\<providerOption> Element</span></span>
<span data-ttu-id="04f8d-103">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="04f8d-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="04f8d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04f8d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04f8d-105">&nbsp;&nbsp;[ **\<> System. codedom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="04f8d-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="04f8d-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**compiladores**](compilers-element.md) ></span><span class="sxs-lookup"><span data-stu-id="04f8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\</span></span>
<span data-ttu-id="04f8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**compilador**](compiler-element.md) ></span><span class="sxs-lookup"><span data-stu-id="04f8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="04f8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption >**</span><span class="sxs-lookup"><span data-stu-id="04f8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="04f8d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04f8d-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04f8d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04f8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04f8d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04f8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04f8d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="04f8d-112">Attributes</span></span>  
  
|<span data-ttu-id="04f8d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="04f8d-113">Attribute</span></span>|<span data-ttu-id="04f8d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="04f8d-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="04f8d-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="04f8d-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="04f8d-116">Especifica el nombre de la opción; por ejemplo, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="04f8d-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="04f8d-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="04f8d-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="04f8d-118">Especifica el valor de la opción; por ejemplo, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="04f8d-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04f8d-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04f8d-119">Child Elements</span></span>  
 <span data-ttu-id="04f8d-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="04f8d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04f8d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04f8d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="04f8d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="04f8d-122">Element</span></span>|<span data-ttu-id="04f8d-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="04f8d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04f8d-124">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="04f8d-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="04f8d-125">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04f8d-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="04f8d-126">\<elemento > System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="04f8d-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="04f8d-127">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="04f8d-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="04f8d-128">\<compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="04f8d-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="04f8d-129">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos `<compiler>`.</span><span class="sxs-lookup"><span data-stu-id="04f8d-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="04f8d-130">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="04f8d-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="04f8d-131">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="04f8d-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04f8d-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04f8d-132">Remarks</span></span>  
 <span data-ttu-id="04f8d-133">En los proveedores de código .NET Framework versión 3,5, Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor mediante el elemento `<providerOption>`.</span><span class="sxs-lookup"><span data-stu-id="04f8d-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="04f8d-134">El .NET Framework 3,5 incluye ensamblados de .NET Framework 2,0 actualizados y proporciona nuevos ensamblados de la versión 3,5 que contienen nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="04f8d-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="04f8d-135">Los proveedores C# de código de Microsoft y Visual Basic se encuentran en .NET Framework ensamblados 2,0, pero se han actualizado para admitir los compiladores de la versión 3,5.</span><span class="sxs-lookup"><span data-stu-id="04f8d-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="04f8d-136">De forma predeterminada, los proveedores de código actualizados generan código para los compiladores de la versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="04f8d-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="04f8d-137">Puede usar el elemento `<providerOption>` para cambiar la versión del compilador de destino a 3,5.</span><span class="sxs-lookup"><span data-stu-id="04f8d-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="04f8d-138">Para ello, especifique "CompilerVersion" para el atributo `name` y "v 3.5" para el atributo `value`.</span><span class="sxs-lookup"><span data-stu-id="04f8d-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="04f8d-139">Debe preceder el número de versión con una "v" en minúscula.</span><span class="sxs-lookup"><span data-stu-id="04f8d-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="04f8d-140">Para hacer que la especificación de la versión sea global, agregue el elemento `<providerOption>` al archivo Machine. config de la .NET Framework 2,0 o a la raíz del archivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="04f8d-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="04f8d-141">Si actualiza la versión predeterminada del compilador a 3,5 en el archivo Machine. config, puede volver a cambiarla a 2,0 por aplicación mediante el elemento `<providerOption>` del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="04f8d-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="04f8d-142">Los implementadores de proveedores de código CodeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un parámetro `providerOptions` de tipo <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="04f8d-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04f8d-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04f8d-143">Example</span></span>  
 <span data-ttu-id="04f8d-144">En el ejemplo siguiente se muestra cómo especificar que se debe usar C# la versión 3,5 del proveedor de código.</span><span class="sxs-lookup"><span data-stu-id="04f8d-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04f8d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="04f8d-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="04f8d-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="04f8d-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="04f8d-147">\<compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="04f8d-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="04f8d-148">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="04f8d-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="04f8d-149">[Elemento Compiler para compiladores para compilation (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="04f8d-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
