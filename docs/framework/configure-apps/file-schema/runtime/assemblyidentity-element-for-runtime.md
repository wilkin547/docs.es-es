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
ms.openlocfilehash: 939e10e0c06e98f98e0c468358f4296fd1061a79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593932"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="d957a-102">&lt;assemblyIdentity&gt; (elemento) para &lt;en tiempo de ejecución&gt;</span><span class="sxs-lookup"><span data-stu-id="d957a-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="d957a-103">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="d957a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d957a-104">\<configuration></span></span>  
<span data-ttu-id="d957a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d957a-105">\<runtime></span></span>  
<span data-ttu-id="d957a-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="d957a-106">\<assemblyBinding></span></span>  
<span data-ttu-id="d957a-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="d957a-107">\<dependentAssembly></span></span>  
<span data-ttu-id="d957a-108">\<assemblyIdentity></span><span class="sxs-lookup"><span data-stu-id="d957a-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d957a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d957a-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d957a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d957a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d957a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d957a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d957a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d957a-112">Attributes</span></span>  
  
|<span data-ttu-id="d957a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d957a-113">Attribute</span></span>|<span data-ttu-id="d957a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d957a-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d957a-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d957a-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="d957a-116">El nombre del ensamblado</span><span class="sxs-lookup"><span data-stu-id="d957a-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="d957a-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d957a-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d957a-118">Cadena que especifica el idioma y país o región del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="d957a-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d957a-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d957a-120">Un valor hexadecimal que especifica el nombre seguro del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="d957a-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d957a-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d957a-122">Uno de los valores "x86", "amd64", "msil" o "ia64", que se especifica la arquitectura de procesador para un ensamblado que contiene código específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="d957a-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="d957a-123">Los valores no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d957a-123">The values are not case-sensitive.</span></span> <span data-ttu-id="d957a-124">Si el atributo se asigna a cualquier otro valor, toda la `<assemblyIdentity>` se omite el elemento.</span><span class="sxs-lookup"><span data-stu-id="d957a-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="d957a-125">Vea <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="d957a-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="d957a-126">Atributo processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="d957a-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="d957a-127">Valor</span><span class="sxs-lookup"><span data-stu-id="d957a-127">Value</span></span>|<span data-ttu-id="d957a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d957a-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="d957a-129">AMD 64 x86 sólo arquitectura.</span><span class="sxs-lookup"><span data-stu-id="d957a-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="d957a-130">Arquitectura de Itanium de Intel.</span><span class="sxs-lookup"><span data-stu-id="d957a-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="d957a-131">Neutral respecto al procesador y bits por palabra.</span><span class="sxs-lookup"><span data-stu-id="d957a-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="d957a-132">Un x86 32-bit procesador, o nativo o en el Windows en el entorno de Windows (WOW) en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d957a-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d957a-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d957a-133">Child Elements</span></span>  
 <span data-ttu-id="d957a-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d957a-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d957a-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d957a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d957a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="d957a-136">Element</span></span>|<span data-ttu-id="d957a-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="d957a-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="d957a-138">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d957a-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="d957a-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d957a-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="d957a-140">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="d957a-141">Utilice uno `<dependentAssembly>` (elemento) para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="d957a-142">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d957a-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d957a-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d957a-143">Remarks</span></span>  
 <span data-ttu-id="d957a-144">Cada  **\<dependentAssembly >** elemento debe tener una  **\<assemblyIdentity >** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="d957a-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="d957a-145">Si el `processorArchitecture` atributo está presente, el `<assemblyIdentity>` elemento se aplica solo al ensamblado con la arquitectura del procesador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d957a-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="d957a-146">Si el `processorArchitecture` atributo no está presente, el `<assemblyIdentity>` elemento puede aplicarse a un ensamblado con cualquier arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="d957a-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="d957a-147">El ejemplo siguiente muestra un archivo de configuración para los dos ensamblados con el mismo nombre que tienen como destino dos arquitecturas diferentes de un procesador de dos y cuyas versiones no se haya mantenido en sincronía. Cuando la aplicación se ejecuta en el x86 la primera plataforma `<assemblyIdentity>` se aplica el elemento y se omite el resto.</span><span class="sxs-lookup"><span data-stu-id="d957a-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="d957a-148">Si la aplicación se ejecuta en una plataforma distinta x86 o ia64, ambos se omiten.</span><span class="sxs-lookup"><span data-stu-id="d957a-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="d957a-149">Si un archivo de configuración contiene un `<assemblyIdentity>` elemento sin ningún `processorArchitecture` de atributo y no contiene un elemento que coincide con la plataforma, el elemento sin el `processorArchitecture` se usa el atributo.</span><span class="sxs-lookup"><span data-stu-id="d957a-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d957a-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d957a-150">Example</span></span>  
 <span data-ttu-id="d957a-151">El ejemplo siguiente muestra cómo proporcionar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d957a-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d957a-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="d957a-152">See also</span></span>
- [<span data-ttu-id="d957a-153">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d957a-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d957a-154">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d957a-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d957a-155">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="d957a-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
