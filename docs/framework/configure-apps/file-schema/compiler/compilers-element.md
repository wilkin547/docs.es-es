---
title: '&lt;los compiladores&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8ce303d33a83d972247609e5d02d16a4a57669ff
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47083799"
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="28896-102">&lt;los compiladores&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="28896-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="28896-103">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="28896-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="28896-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="28896-104">\<configuration></span></span>  
<span data-ttu-id="28896-105">\<System.CodeDom ></span><span class="sxs-lookup"><span data-stu-id="28896-105">\<system.codedom></span></span>  
<span data-ttu-id="28896-106">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="28896-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28896-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28896-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28896-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28896-108">Attributes and Elements</span></span>  
 <span data-ttu-id="28896-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28896-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28896-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="28896-110">Attributes</span></span>  
 <span data-ttu-id="28896-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28896-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28896-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28896-112">Child Elements</span></span>  
  
|<span data-ttu-id="28896-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="28896-113">Element</span></span>|<span data-ttu-id="28896-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="28896-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28896-115">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="28896-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="28896-116">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="28896-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28896-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28896-117">Parent Elements</span></span>  
  
|<span data-ttu-id="28896-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="28896-118">Element</span></span>|<span data-ttu-id="28896-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="28896-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28896-120">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="28896-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="28896-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28896-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="28896-122">\<System.CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="28896-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="28896-123">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="28896-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28896-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28896-124">Remarks</span></span>  
 <span data-ttu-id="28896-125">El [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene los valores de configuración de compilador para los proveedores de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="28896-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="28896-126">Cada [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="28896-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="28896-127">.NET Framework define la inicial del compilador y la configuración del proveedor de lenguaje en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="28896-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="28896-128">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28896-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="28896-129">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="28896-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="28896-130">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="28896-130">Configuration File</span></span>  
 <span data-ttu-id="28896-131">Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="28896-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28896-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28896-132">Example</span></span>  
 <span data-ttu-id="28896-133">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="28896-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28896-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="28896-134">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="28896-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="28896-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="28896-136">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="28896-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="28896-137">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="28896-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
