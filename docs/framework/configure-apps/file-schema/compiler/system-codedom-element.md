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
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149574"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="25428-102">\<system.codedom> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="25428-102">\<system.codedom> Element</span></span>

<span data-ttu-id="25428-103">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="25428-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="25428-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25428-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25428-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="25428-105">Attributes and Elements</span></span>  

 <span data-ttu-id="25428-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="25428-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25428-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="25428-107">Attributes</span></span>  

 <span data-ttu-id="25428-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="25428-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25428-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="25428-109">Child Elements</span></span>  
  
|<span data-ttu-id="25428-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="25428-110">Element</span></span>|<span data-ttu-id="25428-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="25428-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="25428-112">Contenedor para los elementos de configuración del compilador; contiene cero o más [\<compiler>](compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="25428-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25428-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="25428-113">Parent Elements</span></span>  
  
|<span data-ttu-id="25428-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="25428-114">Element</span></span>|<span data-ttu-id="25428-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="25428-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="25428-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25428-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25428-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25428-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="25428-118">.NET Framework versión 2,0</span><span class="sxs-lookup"><span data-stu-id="25428-118">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="25428-119">El [\<system.codedom>](system-codedom-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes instalados en un equipo, además de los proveedores predeterminados que se instalan con el .NET Framework, como <xref:Microsoft.CSharp.CSharpCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="25428-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="25428-120">El [\<compilers>](compilers-element.md) elemento contiene cero o más [\<compiler>](compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="25428-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="25428-121">Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="25428-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="25428-122">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración al archivo de configuración del equipo (Machine.config) para una nueva <xref:System.CodeDom.Compiler.CodeDomProvider> implementación.</span><span class="sxs-lookup"><span data-stu-id="25428-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="25428-123">Utilice el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguajes identificados por los valores de configuración del compilador en un equipo.</span><span class="sxs-lookup"><span data-stu-id="25428-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25428-124">En las versiones .NET Framework 1,0 y 1,1, los proveedores de lenguajes predeterminados proporcionados por el .NET Framework se identifican en el [\<compilers>](compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="25428-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="25428-125">En el .NET Framework versión 2,0, los proveedores de lenguajes predeterminados no se identifican en el [\<compilers>](compilers-element.md) elemento, pero se pueden enumerar mediante el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> método.</span><span class="sxs-lookup"><span data-stu-id="25428-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="25428-126">.NET Framework versiones 1,0 y 1,1</span><span class="sxs-lookup"><span data-stu-id="25428-126">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="25428-127">El [\<system.codedom>](system-codedom-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo.</span><span class="sxs-lookup"><span data-stu-id="25428-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="25428-128">El [\<compilers>](compilers-element.md) elemento contiene cero o más [\<compiler>](compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="25428-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="25428-129">Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="25428-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="25428-130">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="25428-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="25428-131">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="25428-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="25428-132">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="25428-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="25428-133">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="25428-133">Configuration File</span></span>  

 <span data-ttu-id="25428-134">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25428-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25428-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25428-135">Example</span></span>  

 <span data-ttu-id="25428-136">En el ejemplo siguiente se muestra una configuración típica del compilador.</span><span class="sxs-lookup"><span data-stu-id="25428-136">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25428-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="25428-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="25428-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="25428-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="25428-139">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="25428-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="25428-140">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="25428-140">\<compiler> Element</span></span>](compiler-element.md)
