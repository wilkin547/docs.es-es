---
title: '&lt;compilador&gt; elemento'
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
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 242a4780443026e751d76c7e80dd9a77cbbbddc7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="9ed0c-102">&lt;compilador&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="9ed0c-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="9ed0c-103">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="9ed0c-104">\<Elemento de configuración ></span><span class="sxs-lookup"><span data-stu-id="9ed0c-104">\<configuration Element></span></span>  
<span data-ttu-id="9ed0c-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="9ed0c-105">\<system.codedom Element></span></span>  
<span data-ttu-id="9ed0c-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="9ed0c-106">\<compilers Element></span></span>  
<span data-ttu-id="9ed0c-107">\<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="9ed0c-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed0c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ed0c-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ed0c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ed0c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9ed0c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ed0c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ed0c-111">Attributes</span></span>  
  
|<span data-ttu-id="9ed0c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ed0c-112">Attribute</span></span>|<span data-ttu-id="9ed0c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ed0c-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="9ed0c-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9ed0c-115">Especifica los argumentos específicos del compilador adicionales para la compilación.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="9ed0c-116">Los valores para el `compilerOptions` atributo normalmente se muestran en un tema de opciones del compilador para que el compilador.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="9ed0c-117">En la documentación de Visual Studio 2005, puede localizar las opciones del compilador, busque "opciones del compilador" en el índice.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="9ed0c-118">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ed0c-119">Proporciona una lista separada por comas de extensiones de nombre de archivo utilizado por los archivos de origen para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="9ed0c-120">Por ejemplo, ". cs".</span><span class="sxs-lookup"><span data-stu-id="9ed0c-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="9ed0c-121">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ed0c-122">Proporciona una lista separada por comas de nombres de los idiomas admitidos por el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="9ed0c-123">Por ejemplo, "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="9ed0c-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="9ed0c-124">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ed0c-125">Especifica el nombre de tipo del proveedor de lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="9ed0c-126">El nombre de tipo debe cumplir los requisitos definidos en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="9ed0c-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="9ed0c-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9ed0c-128">Especifica el nivel de advertencia del compilador predeterminado; Determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ed0c-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ed0c-129">Child Elements</span></span>  
  
|<span data-ttu-id="9ed0c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ed0c-130">Element</span></span>|<span data-ttu-id="9ed0c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ed0c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ed0c-132">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="9ed0c-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="9ed0c-133">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ed0c-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ed0c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="9ed0c-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ed0c-135">Element</span></span>|<span data-ttu-id="9ed0c-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ed0c-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ed0c-137">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="9ed0c-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9ed0c-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9ed0c-139">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="9ed0c-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="9ed0c-140">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="9ed0c-141">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="9ed0c-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="9ed0c-142">Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ed0c-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ed0c-143">Remarks</span></span>  
 <span data-ttu-id="9ed0c-144">Cada `<compiler>` elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="9ed0c-145">Extiende el proveedor de la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un idioma específico; el `<compiler>` elemento define la configuración de generador de código para el proveedor de lenguaje y compilador.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="9ed0c-146">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9ed0c-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="9ed0c-147">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="9ed0c-148">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="9ed0c-149">Elementos de compilador de la aplicación o el archivo de configuración Web pueden complementar o reemplazar la configuración en el archivo de configuración de equipo.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="9ed0c-150">Si se configura más de una implementación de proveedor para el mismo nombre de lenguaje o la misma extensión de archivo, la última configuración coincidente invalida cualquier proveedor configurado anteriormente para esa extensión de archivo o nombre de idioma.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9ed0c-151">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="9ed0c-151">Configuration File</span></span>  
 <span data-ttu-id="9ed0c-152">Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ed0c-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ed0c-153">Example</span></span>  
 <span data-ttu-id="9ed0c-154">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="9ed0c-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ed0c-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ed0c-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="9ed0c-156">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9ed0c-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9ed0c-157">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="9ed0c-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="9ed0c-158">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="9ed0c-158">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 <span data-ttu-id="9ed0c-159">[Elemento Compiler aplicado a compilers para compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9ed0c-159">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span></span>
