---
title: '&lt;qualifyAssembly&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dd24ae9e5659deff7ddbe4183c70d5b442542cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="c6063-102">&lt;qualifyAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="c6063-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="c6063-103">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="c6063-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="c6063-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c6063-104">\<configuration></span></span>  
<span data-ttu-id="c6063-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="c6063-105">\<runtime></span></span>  
<span data-ttu-id="c6063-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="c6063-106">\<assemblyBinding></span></span>  
<span data-ttu-id="c6063-107">\<qualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="c6063-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6063-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6063-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6063-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c6063-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6063-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c6063-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6063-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c6063-111">Attributes</span></span>  
  
|<span data-ttu-id="c6063-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c6063-112">Attribute</span></span>|<span data-ttu-id="c6063-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6063-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="c6063-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c6063-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6063-115">Especifica el nombre parcial del ensamblado tal y como aparece en el código.</span><span class="sxs-lookup"><span data-stu-id="c6063-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="c6063-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c6063-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6063-117">Especifica el nombre completo del ensamblado tal y como aparece en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c6063-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6063-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c6063-118">Child Elements</span></span>  
 <span data-ttu-id="c6063-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6063-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6063-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c6063-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c6063-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6063-121">Element</span></span>|<span data-ttu-id="c6063-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6063-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c6063-123">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c6063-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c6063-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6063-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c6063-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c6063-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6063-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6063-126">Remarks</span></span>  
 <span data-ttu-id="c6063-127">Llamar a la <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> método utilizando nombres de ensamblado parciales hace common language runtime buscar el ensamblado sólo en el directorio de base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6063-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="c6063-128">Use la  **\<qualifyAssembly >** elemento en el archivo de configuración de aplicación para proporcionar la información de ensamblado completo (nombre, versión, referencia cultural y token de clave pública) y hacer que common language runtime buscar el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c6063-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="c6063-129">El **fullName** atributo debe incluir los cuatro campos de identidad del ensamblado: nombre, versión, token de clave pública y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="c6063-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="c6063-130">El **partialName** atributo parcialmente debe hacer referencia a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6063-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="c6063-131">Debe especificar al menos el nombre del ensamblado texto (el caso más común), pero también puede incluir versión, token de clave pública, o referencia cultural (o cualquier combinación de las cuatro, pero no los cuatro).</span><span class="sxs-lookup"><span data-stu-id="c6063-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="c6063-132">El **partialName** debe coincidir con el nombre especificado en la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6063-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="c6063-133">Por ejemplo, no se puede especificar `"math"` como el **partialName** atributo del archivo de configuración y llame `Assembly.Load("math, Version=3.3.3.3")` en el código.</span><span class="sxs-lookup"><span data-stu-id="c6063-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6063-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6063-134">Example</span></span>  
 <span data-ttu-id="c6063-135">En el ejemplo siguiente se convierte de manera lógica la llamada `Assembly.Load("math")` en `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="c6063-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6063-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6063-136">See Also</span></span>  
 [<span data-ttu-id="c6063-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c6063-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="c6063-138">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="c6063-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="c6063-139">NIB: Referencias a ensamblados parciales</span><span class="sxs-lookup"><span data-stu-id="c6063-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/library/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
