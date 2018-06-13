---
title: '&lt;assemblyIdentity&gt; (elemento) para &lt;en tiempo de ejecución&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5d985d1620b7dec324c0113bcd5652cede044950
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744972"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="dc7a7-102">&lt;assemblyIdentity&gt; (elemento) para &lt;en tiempo de ejecución&gt;</span><span class="sxs-lookup"><span data-stu-id="dc7a7-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="dc7a7-103">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="dc7a7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc7a7-104">\<configuration></span></span>  
<span data-ttu-id="dc7a7-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="dc7a7-105">\<runtime></span></span>  
<span data-ttu-id="dc7a7-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="dc7a7-106">\<assemblyBinding></span></span>  
<span data-ttu-id="dc7a7-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="dc7a7-107">\<dependentAssembly></span></span>  
<span data-ttu-id="dc7a7-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="dc7a7-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc7a7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc7a7-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc7a7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc7a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dc7a7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc7a7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc7a7-112">Attributes</span></span>  
  
|<span data-ttu-id="dc7a7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc7a7-113">Attribute</span></span>|<span data-ttu-id="dc7a7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc7a7-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="dc7a7-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="dc7a7-116">El nombre del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dc7a7-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="dc7a7-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dc7a7-118">Una cadena que especifica el idioma y país o región del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="dc7a7-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dc7a7-120">Un valor hexadecimal que especifica el nombre seguro del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="dc7a7-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dc7a7-122">Uno de los valores "x86", "amd64", "msil" o "ia64", que se especifica la arquitectura de procesador para un ensamblado que contiene código específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="dc7a7-123">Los valores no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-123">The values are not case-sensitive.</span></span> <span data-ttu-id="dc7a7-124">Si el atributo se asigna cualquier otro valor, toda la matriz `<assemblyIdentity>` se omite el elemento.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="dc7a7-125">Vea <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="dc7a7-126">Atributo processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="dc7a7-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="dc7a7-127">Valor</span><span class="sxs-lookup"><span data-stu-id="dc7a7-127">Value</span></span>|<span data-ttu-id="dc7a7-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc7a7-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="dc7a7-129">Un procesador AMD de 64 bits sólo.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-129">A 64-bit AMD processor only.</span></span>|  
|`ia64`|<span data-ttu-id="dc7a7-130">Un procesador Intel de 64 bits sólo.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-130">A 64-bit Intel processor only.</span></span>|  
|`msil`|<span data-ttu-id="dc7a7-131">Neutral con respecto al procesador y los bits por palabra</span><span class="sxs-lookup"><span data-stu-id="dc7a7-131">Neutral with respect to processor and bits-per-word</span></span>|  
|`x86`|<span data-ttu-id="dc7a7-132">Un procesador Intel de 32 bits, ya sea nativo o en el entorno Windows on Windows (WOW) en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-132">A 32-bit Intel processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc7a7-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc7a7-133">Child Elements</span></span>  
 <span data-ttu-id="dc7a7-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc7a7-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc7a7-135">Parent Elements</span></span>  
  
|<span data-ttu-id="dc7a7-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc7a7-136">Element</span></span>|<span data-ttu-id="dc7a7-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc7a7-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="dc7a7-138">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="dc7a7-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="dc7a7-140">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="dc7a7-141">Utilice uno `<dependentAssembly>` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="dc7a7-142">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc7a7-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc7a7-143">Remarks</span></span>  
 <span data-ttu-id="dc7a7-144">Cada  **\<dependentAssembly >** elemento debe tener una  **\<assemblyIdentity >** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="dc7a7-145">Si el `processorArchitecture` atributo está presente, el `<assemblyIdentity>` elemento se aplica únicamente al ensamblado con la arquitectura del procesador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="dc7a7-146">Si el `processorArchitecture` atributo no está presente, el `<assemblyIdentity>` elemento puede aplicar a un ensamblado con cualquier arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="dc7a7-147">En el ejemplo siguiente se muestra un archivo de configuración para dos ensamblados con el mismo nombre que destinan a dos arquitecturas de procesador de dos diferentes y cuyas versiones no se han mantenido sincronizadas. Cuando la aplicación se ejecuta en el x86 plataforma la primera `<assemblyIdentity>` elemento se aplica y la otra se omite.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="dc7a7-148">Si la aplicación se ejecuta en una plataforma distinta x86 o ia64, ambos se omiten.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="dc7a7-149">Si un archivo de configuración contiene un `<assemblyIdentity>` elemento sin ningún `processorArchitecture` de atributo y no contiene un elemento que coincida con la plataforma, el elemento sin el `processorArchitecture` se utiliza el atributo.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc7a7-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc7a7-150">Example</span></span>  
 <span data-ttu-id="dc7a7-151">En el ejemplo siguiente se muestra cómo proporcionar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc7a7-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc7a7-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc7a7-152">See Also</span></span>  
 [<span data-ttu-id="dc7a7-153">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="dc7a7-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="dc7a7-154">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="dc7a7-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="dc7a7-155">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="dc7a7-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
