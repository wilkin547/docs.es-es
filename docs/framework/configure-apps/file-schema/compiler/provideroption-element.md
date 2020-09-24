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
ms.openlocfilehash: 9374fbaf7ceb61e5b72335417d32a08525477e0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149639"
---
# <a name="provideroption-element"></a><span data-ttu-id="99d24-102">\<providerOption> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="99d24-102">\<providerOption> Element</span></span>

<span data-ttu-id="99d24-103">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="99d24-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="99d24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99d24-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99d24-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99d24-105">Attributes and Elements</span></span>  

 <span data-ttu-id="99d24-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99d24-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99d24-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="99d24-107">Attributes</span></span>  
  
|<span data-ttu-id="99d24-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="99d24-108">Attribute</span></span>|<span data-ttu-id="99d24-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="99d24-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="99d24-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="99d24-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="99d24-111">Especifica el nombre de la opción; por ejemplo, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="99d24-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="99d24-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="99d24-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="99d24-113">Especifica el valor de la opción; por ejemplo, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="99d24-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99d24-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99d24-114">Child Elements</span></span>  

 <span data-ttu-id="99d24-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99d24-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99d24-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99d24-116">Parent Elements</span></span>  
  
|<span data-ttu-id="99d24-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="99d24-117">Element</span></span>|<span data-ttu-id="99d24-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="99d24-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99d24-119">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="99d24-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="99d24-120">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99d24-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="99d24-121">Elemento \<system.codedom></span><span class="sxs-lookup"><span data-stu-id="99d24-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="99d24-122">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="99d24-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="99d24-123">Elemento \<compilers></span><span class="sxs-lookup"><span data-stu-id="99d24-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="99d24-124">Contenedor para los elementos de configuración del compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="99d24-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="99d24-125">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="99d24-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="99d24-126">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="99d24-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99d24-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99d24-127">Remarks</span></span>  

 <span data-ttu-id="99d24-128">En los proveedores de código .NET Framework versión 3,5, Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor mediante el `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="99d24-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="99d24-129">El .NET Framework 3,5 incluye ensamblados de .NET Framework 2,0 actualizados y proporciona nuevos ensamblados de la versión 3,5 que contienen nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="99d24-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="99d24-130">Los proveedores de código de Microsoft C# y Visual Basic se encuentran en .NET Framework ensamblados 2,0, pero se han actualizado para admitir los compiladores de la versión 3,5.</span><span class="sxs-lookup"><span data-stu-id="99d24-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="99d24-131">De forma predeterminada, los proveedores de código actualizados generan código para los compiladores de la versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="99d24-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="99d24-132">Puede usar el `<providerOption>` elemento para cambiar la versión del compilador de destino a 3,5.</span><span class="sxs-lookup"><span data-stu-id="99d24-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="99d24-133">Para ello, especifique "CompilerVersion" para el `name` atributo y "v 3.5" para el `value` atributo.</span><span class="sxs-lookup"><span data-stu-id="99d24-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="99d24-134">Debe preceder el número de versión con una "v" en minúscula.</span><span class="sxs-lookup"><span data-stu-id="99d24-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="99d24-135">Puede crear la especificación de la versión global agregando el `<providerOption>` elemento al .NET Framework 2,0 Machine.config o Web.config raíz.</span><span class="sxs-lookup"><span data-stu-id="99d24-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="99d24-136">Si actualiza la versión predeterminada del compilador a 3,5 en el archivo Machine.config, puede volver a cambiarla a 2,0 por aplicación mediante el `<providerOption>` elemento del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="99d24-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="99d24-137">Los implementadores de proveedores de código CodeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un `providerOptions` parámetro de tipo <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="99d24-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99d24-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99d24-138">Example</span></span>  

 <span data-ttu-id="99d24-139">En el ejemplo siguiente se muestra cómo especificar que se debe usar la versión 3,5 del proveedor de código de C#.</span><span class="sxs-lookup"><span data-stu-id="99d24-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99d24-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="99d24-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="99d24-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="99d24-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="99d24-142">Elemento \<compilers></span><span class="sxs-lookup"><span data-stu-id="99d24-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="99d24-143">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="99d24-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="99d24-144">[Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="99d24-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
