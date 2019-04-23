---
title: <compilers> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 744ef0d9bc58e6a0152dce53c40c24eb5283dc0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130525"
---
# <a name="compilers-element"></a><span data-ttu-id="4777c-102">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="4777c-102">\<compilers> Element</span></span>
<span data-ttu-id="4777c-103">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="4777c-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="4777c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4777c-104">\<configuration></span></span>  
<span data-ttu-id="4777c-105">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="4777c-105">\<system.codedom></span></span>  
<span data-ttu-id="4777c-106">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="4777c-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4777c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4777c-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4777c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4777c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4777c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4777c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4777c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4777c-110">Attributes</span></span>  
 <span data-ttu-id="4777c-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4777c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4777c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4777c-112">Child Elements</span></span>  
  
|<span data-ttu-id="4777c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4777c-113">Element</span></span>|<span data-ttu-id="4777c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4777c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4777c-115">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="4777c-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="4777c-116">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4777c-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4777c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4777c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4777c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4777c-118">Element</span></span>|<span data-ttu-id="4777c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4777c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4777c-120">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="4777c-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="4777c-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4777c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="4777c-122">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="4777c-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="4777c-123">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="4777c-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4777c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4777c-124">Remarks</span></span>  
 <span data-ttu-id="4777c-125">El [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene los valores de configuración de compilador para los proveedores de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="4777c-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="4777c-126">Cada [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="4777c-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="4777c-127">.NET Framework define la inicial del compilador y la configuración del proveedor de lenguaje en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4777c-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4777c-128">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4777c-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="4777c-129">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="4777c-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4777c-130">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4777c-130">Configuration File</span></span>  
 <span data-ttu-id="4777c-131">Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4777c-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4777c-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4777c-132">Example</span></span>  
 <span data-ttu-id="4777c-133">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="4777c-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4777c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4777c-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="4777c-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4777c-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4777c-136">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="4777c-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="4777c-137">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="4777c-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
