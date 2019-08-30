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
ms.openlocfilehash: 5232c5bd2d4fad8104d156bfa86141ceb7f0dd93
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "70167690"
---
# <a name="compilers-element"></a><span data-ttu-id="75119-102">\<compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="75119-102">\<compilers> Element</span></span>
<span data-ttu-id="75119-103">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="75119-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  
  
[<span data-ttu-id="75119-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="75119-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="75119-105">&nbsp;&nbsp;[ **\<> System. CodeDom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="75119-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="75119-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<compiladores >**</span><span class="sxs-lookup"><span data-stu-id="75119-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75119-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75119-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75119-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75119-108">Attributes and Elements</span></span>  
 <span data-ttu-id="75119-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75119-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75119-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="75119-110">Attributes</span></span>  
 <span data-ttu-id="75119-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75119-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75119-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75119-112">Child Elements</span></span>  
  
|<span data-ttu-id="75119-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="75119-113">Element</span></span>|<span data-ttu-id="75119-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75119-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75119-115">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="75119-115">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="75119-116">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="75119-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75119-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75119-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75119-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="75119-118">Element</span></span>|<span data-ttu-id="75119-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="75119-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75119-120">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="75119-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="75119-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75119-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="75119-122">\<Elemento > de System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="75119-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="75119-123">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="75119-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75119-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75119-124">Remarks</span></span>  
 <span data-ttu-id="75119-125">El elemento compiladores > contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo. [ \<](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="75119-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="75119-126">Cada elemento > del compilador especifica los atributos de configuración del compilador para un proveedor de lenguaje concreto. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="75119-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="75119-127">El .NET Framework define la configuración inicial del compilador y del proveedor de lenguaje en el archivo de configuración del equipo (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="75119-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="75119-128">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="75119-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="75119-129">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="75119-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="75119-130">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="75119-130">Configuration File</span></span>  
 <span data-ttu-id="75119-131">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75119-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75119-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75119-132">Example</span></span>  
 <span data-ttu-id="75119-133">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="75119-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75119-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="75119-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="75119-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="75119-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="75119-136">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="75119-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="75119-137">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="75119-137">\<compiler> Element</span></span>](compiler-element.md)
