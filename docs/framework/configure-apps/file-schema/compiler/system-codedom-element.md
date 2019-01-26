---
title: '&lt;system.codedom&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 1a97b20ae1f4e5c85d678f559cf0f7d69cfff4e1
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083956"
---
# <a name="ltsystemcodedomgt-element"></a><span data-ttu-id="0eafe-102">&lt;system.codedom&gt; Element</span><span class="sxs-lookup"><span data-stu-id="0eafe-102">&lt;system.codedom&gt; Element</span></span>
<span data-ttu-id="0eafe-103">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="0eafe-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="0eafe-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="0eafe-104">\<configuration> Element</span></span>  
<span data-ttu-id="0eafe-105">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="0eafe-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eafe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eafe-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0eafe-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0eafe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0eafe-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0eafe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0eafe-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0eafe-109">Attributes</span></span>  
 <span data-ttu-id="0eafe-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0eafe-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0eafe-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0eafe-111">Child Elements</span></span>  
  
|<span data-ttu-id="0eafe-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="0eafe-112">Element</span></span>|<span data-ttu-id="0eafe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eafe-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0eafe-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="0eafe-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="0eafe-115">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="0eafe-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0eafe-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0eafe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0eafe-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0eafe-117">Element</span></span>|<span data-ttu-id="0eafe-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eafe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0eafe-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0eafe-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="0eafe-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0eafe-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eafe-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0eafe-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="0eafe-122">Versión de .NET framework 2.0</span><span class="sxs-lookup"><span data-stu-id="0eafe-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="0eafe-123">El [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene la configuración de compilador para los proveedores de lenguaje instalados en un equipo, además de los proveedores predeterminados que se instalan con .NET Framework, como la <xref:Microsoft.CSharp.CSharpCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="0eafe-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="0eafe-124">El [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene cero o más [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="0eafe-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="0eafe-125">Cada [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="0eafe-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="0eafe-126">Los desarrolladores y proveedores de compiladores pueden agregar valores de configuración al archivo de configuración del equipo (Machine.config) para un nuevo <xref:System.CodeDom.Compiler.CodeDomProvider> implementación.</span><span class="sxs-lookup"><span data-stu-id="0eafe-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="0eafe-127">Use el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguaje identificados por los valores de configuración del compilador en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0eafe-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0eafe-128">En las versiones de .NET Framework 1.0 y 1.1, el idioma predeterminado proveedores proporcionados por .NET Framework se identifican en el [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="0eafe-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="0eafe-129">En la versión 2.0 de .NET Framework, los proveedores de lenguaje predeterminado no se identifican en el [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento, pero se pueden enumerar mediante la <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0eafe-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="0eafe-130">Versiones 1.0 y 1.1 de .NET framework</span><span class="sxs-lookup"><span data-stu-id="0eafe-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="0eafe-131">El [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene los valores de configuración de compilador para los proveedores de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0eafe-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="0eafe-132">El [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene cero o más [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="0eafe-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="0eafe-133">Cada [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="0eafe-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="0eafe-134">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0eafe-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="0eafe-135">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="0eafe-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="0eafe-136">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0eafe-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0eafe-137">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0eafe-137">Configuration File</span></span>  
 <span data-ttu-id="0eafe-138">Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0eafe-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eafe-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eafe-139">Example</span></span>  
 <span data-ttu-id="0eafe-140">El ejemplo siguiente ilustra una configuración de compilador típico.</span><span class="sxs-lookup"><span data-stu-id="0eafe-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0eafe-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eafe-141">See also</span></span>
- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="0eafe-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0eafe-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="0eafe-143">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="0eafe-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="0eafe-144">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="0eafe-144">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
