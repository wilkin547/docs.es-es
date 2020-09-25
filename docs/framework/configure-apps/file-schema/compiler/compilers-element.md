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
ms.openlocfilehash: 1aa096e185ae7f5957f173c03e221a31f30d5200
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172949"
---
# <a name="compilers-element"></a><span data-ttu-id="f93ec-102">\<compilers> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="f93ec-102">\<compilers> Element</span></span>

<span data-ttu-id="f93ec-103">Contenedor para los elementos de configuración del compilador; contiene cero o más [\<compiler>](compiler-element.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="f93ec-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="f93ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f93ec-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f93ec-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f93ec-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f93ec-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f93ec-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f93ec-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f93ec-107">Attributes</span></span>  

 <span data-ttu-id="f93ec-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f93ec-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f93ec-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f93ec-109">Child Elements</span></span>  
  
|<span data-ttu-id="f93ec-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f93ec-110">Element</span></span>|<span data-ttu-id="f93ec-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f93ec-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f93ec-112">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="f93ec-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="f93ec-113">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f93ec-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f93ec-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f93ec-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f93ec-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f93ec-115">Element</span></span>|<span data-ttu-id="f93ec-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f93ec-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f93ec-117">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="f93ec-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="f93ec-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f93ec-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="f93ec-119">Elemento \<system.codedom></span><span class="sxs-lookup"><span data-stu-id="f93ec-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="f93ec-120">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="f93ec-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f93ec-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f93ec-121">Remarks</span></span>  

 <span data-ttu-id="f93ec-122">El [\<compilers>](compilers-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo.</span><span class="sxs-lookup"><span data-stu-id="f93ec-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="f93ec-123">Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="f93ec-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="f93ec-124">El .NET Framework define la configuración inicial del compilador y del proveedor de lenguaje en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f93ec-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="f93ec-125">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f93ec-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="f93ec-126">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="f93ec-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f93ec-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f93ec-127">Configuration File</span></span>  

 <span data-ttu-id="f93ec-128">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f93ec-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f93ec-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f93ec-129">Example</span></span>  

 <span data-ttu-id="f93ec-130">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="f93ec-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f93ec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f93ec-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="f93ec-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f93ec-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f93ec-133">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="f93ec-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f93ec-134">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="f93ec-134">\<compiler> Element</span></span>](compiler-element.md)
