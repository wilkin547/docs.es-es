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
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155393"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="cd410-102">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="cd410-102">\<system.codedom> Element</span></span>
<span data-ttu-id="cd410-103">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="cd410-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="cd410-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="cd410-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cd410-105">&nbsp;&nbsp;**\<>system.codedom**</span><span class="sxs-lookup"><span data-stu-id="cd410-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd410-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd410-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd410-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd410-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cd410-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd410-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd410-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd410-109">Attributes</span></span>  
 <span data-ttu-id="cd410-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cd410-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd410-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cd410-111">Child Elements</span></span>  
  
|<span data-ttu-id="cd410-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd410-112">Element</span></span>|<span data-ttu-id="cd410-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd410-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd410-114">\<compiladores></span><span class="sxs-lookup"><span data-stu-id="cd410-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="cd410-115">Contenedor para elementos de configuración del compilador; contiene cero [ \<](compiler-element.md) o más elementos de>del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd410-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd410-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cd410-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cd410-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd410-117">Element</span></span>|<span data-ttu-id="cd410-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd410-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd410-119">\<configuración></span><span class="sxs-lookup"><span data-stu-id="cd410-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="cd410-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd410-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd410-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd410-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="cd410-122">.NET Framework Versión 2.0</span><span class="sxs-lookup"><span data-stu-id="cd410-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="cd410-123"><xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider>El [ \<elemento>system.codedom](system-codedom-element.md) contiene los valores de configuración del compilador para los proveedores de lenguaje instalados en un equipo además de los proveedores predeterminados que se instalan con .NET Framework, como el archivo .</span><span class="sxs-lookup"><span data-stu-id="cd410-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="cd410-124">El [ \<elemento>de compiladores](compilers-element.md) contiene cero o más [ \<](compiler-element.md) elementos de>del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd410-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="cd410-125">Cada elemento [ \<de>del compilador](compiler-element.md) especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="cd410-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="cd410-126">Los desarrolladores y proveedores de compiladores pueden agregar valores <xref:System.CodeDom.Compiler.CodeDomProvider> de configuración al archivo de configuración del equipo (Machine.config) para una nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="cd410-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="cd410-127">Use <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> el método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguaje identificados por la configuración del compilador en un equipo.</span><span class="sxs-lookup"><span data-stu-id="cd410-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd410-128">En las versiones 1.0 y 1.1 de .NET Framework, los proveedores de lenguaje predeterminados proporcionados por .NET Framework se identifican en los [ \<compiladores>](compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="cd410-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="cd410-129">En la versión 2.0 de .NET Framework, los proveedores de lenguaje predeterminados <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> no se identifican en los [ \<compiladores>](compilers-element.md) elemento, pero se pueden enumerar mediante el método.</span><span class="sxs-lookup"><span data-stu-id="cd410-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="cd410-130">Las versiones 1.0 y 1.1 de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cd410-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="cd410-131">El elemento [ \<>system.codedom](system-codedom-element.md) contiene la configuración del compilador para los proveedores de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="cd410-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="cd410-132">El [ \<elemento>de compiladores](compilers-element.md) contiene cero o más [ \<](compiler-element.md) elementos de>del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd410-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="cd410-133">Cada elemento [ \<de>del compilador](compiler-element.md) especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="cd410-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="cd410-134">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cd410-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="cd410-135">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="cd410-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="cd410-136">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="cd410-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cd410-137">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="cd410-137">Configuration File</span></span>  
 <span data-ttu-id="cd410-138">Este elemento se puede utilizar en el archivo de configuración de la máquina y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd410-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd410-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd410-139">Example</span></span>  
 <span data-ttu-id="cd410-140">En el ejemplo siguiente se muestra una configuración típica del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd410-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd410-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd410-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="cd410-142">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="cd410-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cd410-143">Esquema de configuración del compilador y del proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="cd410-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cd410-144">\<compilador> elemento</span><span class="sxs-lookup"><span data-stu-id="cd410-144">\<compiler> Element</span></span>](compiler-element.md)
