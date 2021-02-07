---
description: 'Más información acerca de: <compilers> elemento'
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
ms.openlocfilehash: 6ced6bc81bc7d829ccebab50e0a361985c970f5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699173"
---
# <a name="compilers-element"></a><span data-ttu-id="877cd-103">\<compilers> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="877cd-103">\<compilers> Element</span></span>

<span data-ttu-id="877cd-104">Contenedor para los elementos de configuración del compilador; contiene cero o más [\<compiler>](compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="877cd-104">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="877cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="877cd-105">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="877cd-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="877cd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="877cd-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="877cd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="877cd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="877cd-108">Attributes</span></span>  

 <span data-ttu-id="877cd-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="877cd-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="877cd-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="877cd-110">Child Elements</span></span>  
  
|<span data-ttu-id="877cd-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="877cd-111">Element</span></span>|<span data-ttu-id="877cd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="877cd-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="877cd-113">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="877cd-113">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="877cd-114">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="877cd-114">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="877cd-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="877cd-115">Parent Elements</span></span>  
  
|<span data-ttu-id="877cd-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="877cd-116">Element</span></span>|<span data-ttu-id="877cd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="877cd-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="877cd-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="877cd-118">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="877cd-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="877cd-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="877cd-120">Elemento \<system.codedom></span><span class="sxs-lookup"><span data-stu-id="877cd-120">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="877cd-121">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="877cd-121">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="877cd-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="877cd-122">Remarks</span></span>  

 <span data-ttu-id="877cd-123">El [\<compilers>](compilers-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo.</span><span class="sxs-lookup"><span data-stu-id="877cd-123">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="877cd-124">Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="877cd-124">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="877cd-125">El .NET Framework define la configuración inicial del compilador y del proveedor de lenguaje en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="877cd-125">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="877cd-126">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="877cd-126">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="877cd-127">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="877cd-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="877cd-128">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="877cd-128">Configuration File</span></span>  

 <span data-ttu-id="877cd-129">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="877cd-129">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="877cd-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="877cd-130">Example</span></span>  

 <span data-ttu-id="877cd-131">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="877cd-131">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="877cd-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="877cd-132">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="877cd-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="877cd-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="877cd-134">Esquema de configuración de proveedor de lenguaje y compilador</span><span class="sxs-lookup"><span data-stu-id="877cd-134">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="877cd-135">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="877cd-135">\<compiler> Element</span></span>](compiler-element.md)
