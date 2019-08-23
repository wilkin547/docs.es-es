---
title: Elemento <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 43bc3c40bfc0b0ce4c0b18683092faf8b67e1c04
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927696"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="0e7b9-102">\<Elemento > de System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="0e7b9-102">\<system.codedom> Element</span></span>
<span data-ttu-id="0e7b9-103">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="0e7b9-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="0e7b9-104">\<configuration> Element</span></span>  
<span data-ttu-id="0e7b9-105">\<Elemento > de System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="0e7b9-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7b9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e7b9-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e7b9-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e7b9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0e7b9-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e7b9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e7b9-109">Attributes</span></span>  
 <span data-ttu-id="0e7b9-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e7b9-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e7b9-111">Child Elements</span></span>  
  
|<span data-ttu-id="0e7b9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e7b9-112">Element</span></span>|<span data-ttu-id="0e7b9-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e7b9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e7b9-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="0e7b9-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="0e7b9-115">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="0e7b9-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e7b9-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e7b9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0e7b9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e7b9-117">Element</span></span>|<span data-ttu-id="0e7b9-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e7b9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e7b9-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0e7b9-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="0e7b9-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e7b9-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e7b9-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="0e7b9-122">.NET Framework versión 2,0</span><span class="sxs-lookup"><span data-stu-id="0e7b9-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="0e7b9-123"><xref:Microsoft.CSharp.CSharpCodeProvider> El [ \<elemento > de System. CodeDom](system-codedom-element.md) contiene los valores de configuración del compilador para los proveedores de lenguajes instalados en un equipo, además de los proveedores predeterminados que se instalan con el .NET Framework, como y. <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="0e7b9-124">[ El\<](compilers-element.md) elemento compiladores > contiene cero o más [ \<elementos de > del](compiler-element.md) compilador.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="0e7b9-125">Cada elemento > del compilador especifica los atributos de configuración del compilador para un proveedor de lenguaje concreto. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e7b9-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="0e7b9-126">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración al archivo de configuración del equipo ( <xref:System.CodeDom.Compiler.CodeDomProvider> Machine. config) para una nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="0e7b9-127">Utilice el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguajes identificados por los valores de configuración del compilador en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e7b9-128">En las versiones .NET Framework 1,0 y 1,1, los proveedores de lenguajes predeterminados proporcionados por el [ \<](compilers-element.md) .NET Framework se identifican en el elemento compiladores >.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="0e7b9-129">En el .NET Framework versión 2,0, los proveedores de lenguajes predeterminados no [ \<](compilers-element.md) se identifican en el elemento compiladores >, pero se <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> pueden enumerar mediante el método.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="0e7b9-130">.NET Framework versiones 1,0 y 1,1</span><span class="sxs-lookup"><span data-stu-id="0e7b9-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="0e7b9-131">El elemento > de [System. CodeDom contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo. \<](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e7b9-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="0e7b9-132">[ El\<](compilers-element.md) elemento compiladores > contiene cero o más [ \<elementos de > del](compiler-element.md) compilador.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="0e7b9-133">Cada elemento > del compilador especifica los atributos de configuración del compilador para un proveedor de lenguaje concreto. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e7b9-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="0e7b9-134">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0e7b9-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="0e7b9-135">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="0e7b9-136">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0e7b9-137">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0e7b9-137">Configuration File</span></span>  
 <span data-ttu-id="0e7b9-138">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e7b9-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e7b9-139">Example</span></span>  
 <span data-ttu-id="0e7b9-140">En el ejemplo siguiente se muestra una configuración típica del compilador.</span><span class="sxs-lookup"><span data-stu-id="0e7b9-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e7b9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e7b9-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="0e7b9-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0e7b9-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0e7b9-143">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="0e7b9-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0e7b9-144">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="0e7b9-144">\<compiler> Element</span></span>](compiler-element.md)
