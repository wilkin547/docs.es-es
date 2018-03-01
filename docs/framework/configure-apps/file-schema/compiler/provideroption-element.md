---
title: '&lt;providerOption&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f28b7b43f2f782744a0dbc81bd0b91bbbcd8abba
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="4d7b8-102">&lt;providerOption&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="4d7b8-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="4d7b8-103">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="4d7b8-104">\<Elemento de configuración ></span><span class="sxs-lookup"><span data-stu-id="4d7b8-104">\<configuration Element></span></span>  
<span data-ttu-id="4d7b8-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="4d7b8-105">\<system.codedom Element></span></span>  
<span data-ttu-id="4d7b8-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="4d7b8-106">\<compilers Element></span></span>  
<span data-ttu-id="4d7b8-107">\<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="4d7b8-107">\<compiler> Element</span></span>  
<span data-ttu-id="4d7b8-108">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="4d7b8-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d7b8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d7b8-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d7b8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d7b8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d7b8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d7b8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d7b8-112">Attributes</span></span>  
  
|<span data-ttu-id="4d7b8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d7b8-113">Attribute</span></span>|<span data-ttu-id="4d7b8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b8-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4d7b8-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d7b8-116">Especifica el nombre de la opción; Por ejemplo, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="4d7b8-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="4d7b8-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d7b8-118">Especifica el valor de la opción; Por ejemplo, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="4d7b8-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d7b8-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d7b8-119">Child Elements</span></span>  
 <span data-ttu-id="4d7b8-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d7b8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d7b8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4d7b8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d7b8-122">Element</span></span>|<span data-ttu-id="4d7b8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d7b8-124">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="4d7b8-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="4d7b8-125">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="4d7b8-126">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="4d7b8-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="4d7b8-127">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="4d7b8-128">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="4d7b8-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="4d7b8-129">Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="4d7b8-130">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="4d7b8-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="4d7b8-131">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d7b8-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d7b8-132">Remarks</span></span>  
 <span data-ttu-id="4d7b8-133">En la versión 3.5 de .NET Framework, los proveedores de código Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor mediante el `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="4d7b8-134">.NET Framework 3.5 incluye ensamblados actualizados de .NET Framework 2.0 y proporciona nuevos ensamblados de la versión 3.5 que contienen nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="4d7b8-135">Los proveedores de código de Microsoft C# y Visual Basic se encuentran en los ensamblados de .NET Framework 2.0, pero se han actualizado para admitir los compiladores de la versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="4d7b8-136">De forma predeterminada, los proveedores de código actualizado generan código para compiladores de la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="4d7b8-137">Puede usar el `<providerOption>` elemento para cambiar la versión del compilador de destino a la versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="4d7b8-138">Para ello, especifique "CompilerVersion" para el `name` atributo y "v3.5" para el `value` atributo.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="4d7b8-139">Debe preceder el número de versión con una "v" minúscula.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="4d7b8-140">Puede hacer que la especificación de versión global mediante la adición de la `<providerOption>` elemento al archivo raíz Web.config o Machine.config de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="4d7b8-141">Si ha actualizado la versión de compilador predeterminada a 3.5 en el archivo Machine.config, puede cambiarlo a 2.0 en según la aplicación mediante el uso de la `<providerOption>` elemento en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="4d7b8-142">Los implementadores de proveedor de código de codeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un `providerOptions` parámetro de tipo <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d7b8-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d7b8-143">Example</span></span>  
 <span data-ttu-id="4d7b8-144">En el ejemplo siguiente se muestra cómo especificar que la versión 3.5 del proveedor de código de C# debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4d7b8-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d7b8-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d7b8-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="4d7b8-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d7b8-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="4d7b8-147">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="4d7b8-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="4d7b8-148">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="4d7b8-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="4d7b8-149">Elemento Compiler aplicado a compilers para compilation (ASP.NET Settings Schema)</span><span class="sxs-lookup"><span data-stu-id="4d7b8-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
