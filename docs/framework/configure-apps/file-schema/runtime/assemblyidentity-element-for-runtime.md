---
title: Elemento <assemblyIdentity> para <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154314"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="f4978-102">\<assemblyIdentity> \<Element para el> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f4978-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="f4978-103">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4978-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="f4978-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4978-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f4978-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4978-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f4978-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="f4978-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="f4978-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependienteEnsamblaje>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4978-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="f4978-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span><span class="sxs-lookup"><span data-stu-id="f4978-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4978-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4978-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4978-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f4978-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f4978-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f4978-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4978-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f4978-112">Attributes</span></span>  
  
|<span data-ttu-id="f4978-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f4978-113">Attribute</span></span>|<span data-ttu-id="f4978-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4978-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f4978-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f4978-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="f4978-116">El nombre del ensamblado</span><span class="sxs-lookup"><span data-stu-id="f4978-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="f4978-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f4978-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f4978-118">Cadena que especifica el idioma y el país o región del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4978-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="f4978-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f4978-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f4978-120">Valor hexadecimal que especifica el nombre seguro del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4978-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="f4978-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f4978-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f4978-122">Uno de los valores "x86", "amd64", "msil" o "ia64", especificando la arquitectura del procesador para un ensamblado que contiene código específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="f4978-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="f4978-123">Los valores no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4978-123">The values are not case-sensitive.</span></span> <span data-ttu-id="f4978-124">Si al atributo se le asigna `<assemblyIdentity>` cualquier otro valor, se omite todo el elemento.</span><span class="sxs-lookup"><span data-stu-id="f4978-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="f4978-125">Vea <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="f4978-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="f4978-126">atributo processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="f4978-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="f4978-127">Value</span><span class="sxs-lookup"><span data-stu-id="f4978-127">Value</span></span>|<span data-ttu-id="f4978-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4978-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="f4978-129">Arquitectura AMD x86-64 solamente.</span><span class="sxs-lookup"><span data-stu-id="f4978-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="f4978-130">Sólo arquitectura Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="f4978-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="f4978-131">Neutral respecto al procesador y los bits por palabra.</span><span class="sxs-lookup"><span data-stu-id="f4978-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="f4978-132">Un procesador x86 de 32 bits, ya sea nativo o en el entorno de Windows en Windows (WOW) en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f4978-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4978-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f4978-133">Child Elements</span></span>  
 <span data-ttu-id="f4978-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f4978-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4978-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f4978-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f4978-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4978-136">Element</span></span>|<span data-ttu-id="f4978-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4978-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f4978-138">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f4978-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f4978-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f4978-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="f4978-140">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4978-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="f4978-141">Utilice `<dependentAssembly>` un elemento para cada ensamblaje.</span><span class="sxs-lookup"><span data-stu-id="f4978-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="f4978-142">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f4978-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4978-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4978-143">Remarks</span></span>  
 <span data-ttu-id="f4978-144">Cada \*\* \<elemento dependienteAssembly>\*\* debe tener un \*\* \<elemento secundario assemblyIdentity>.\*\*</span><span class="sxs-lookup"><span data-stu-id="f4978-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="f4978-145">Si `processorArchitecture` el atributo está `<assemblyIdentity>` presente, el elemento solo se aplica al ensamblado con la arquitectura de procesador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f4978-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="f4978-146">Si `processorArchitecture` el atributo no `<assemblyIdentity>` está presente, el elemento se puede aplicar a un ensamblado con cualquier arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="f4978-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="f4978-147">En el ejemplo siguiente se muestra un archivo de configuración para dos ensamblados con el mismo nombre que tienen como destino dos arquitecturas de procesador diferentes y cuyas versiones no se han mantenido en sincronización. Cuando la aplicación se ejecuta en la `<assemblyIdentity>` plataforma x86, se aplica el primer elemento y se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="f4978-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="f4978-148">Si la aplicación se ejecuta en una plataforma distinta de x86 o ia64, se omiten ambas.</span><span class="sxs-lookup"><span data-stu-id="f4978-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="f4978-149">Si un archivo `<assemblyIdentity>` de configuración `processorArchitecture` contiene un elemento sin atributo y no contiene `processorArchitecture` un elemento que coincida con la plataforma, se utiliza el elemento sin el atributo.</span><span class="sxs-lookup"><span data-stu-id="f4978-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4978-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4978-150">Example</span></span>  
 <span data-ttu-id="f4978-151">En el ejemplo siguiente se muestra cómo proporcionar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4978-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f4978-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4978-152">See also</span></span>

- [<span data-ttu-id="f4978-153">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f4978-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f4978-154">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f4978-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f4978-155">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="f4978-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
