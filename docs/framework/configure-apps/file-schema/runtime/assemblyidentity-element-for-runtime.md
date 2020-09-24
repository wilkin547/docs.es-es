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
ms.openlocfilehash: f3e74b05ac0fd7c57963f2aad047ba3f2d63a10a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170186"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="e9362-102">Elemento \<assemblyIdentity> para \<runtime></span><span class="sxs-lookup"><span data-stu-id="e9362-102">\<assemblyIdentity> Element for \<runtime></span></span>

<span data-ttu-id="e9362-103">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-103">Contains identifying information about the assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a><span data-ttu-id="e9362-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9362-104">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9362-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e9362-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e9362-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e9362-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9362-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e9362-107">Attributes</span></span>  
  
|<span data-ttu-id="e9362-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e9362-108">Attribute</span></span>|<span data-ttu-id="e9362-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9362-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e9362-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e9362-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9362-111">Nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-111">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="e9362-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9362-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9362-113">Cadena que especifica el idioma y el país o región del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-113">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="e9362-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9362-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9362-115">Valor hexadecimal que especifica el nombre seguro del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-115">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="e9362-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9362-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9362-117">Uno de los valores "x86", "AMD64", "MSIL" o "ia64", que especifica la arquitectura de procesador para un ensamblado que contiene código específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="e9362-117">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="e9362-118">Los valores no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e9362-118">The values are not case-sensitive.</span></span> <span data-ttu-id="e9362-119">Si el atributo tiene asignado cualquier otro valor, `<assemblyIdentity>` se omite todo el elemento.</span><span class="sxs-lookup"><span data-stu-id="e9362-119">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="e9362-120">Vea <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="e9362-120">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="e9362-121">processorArchitecture (atributo)</span><span class="sxs-lookup"><span data-stu-id="e9362-121">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="e9362-122">Value</span><span class="sxs-lookup"><span data-stu-id="e9362-122">Value</span></span>|<span data-ttu-id="e9362-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9362-123">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="e9362-124">Solo arquitectura de AMD x86-64.</span><span class="sxs-lookup"><span data-stu-id="e9362-124">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="e9362-125">Solo la arquitectura Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="e9362-125">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="e9362-126">Neutral respecto al procesador y los bits por palabra.</span><span class="sxs-lookup"><span data-stu-id="e9362-126">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="e9362-127">Un procesador x86 de 32 bits, ya sea nativo o en el entorno de Windows en Windows (WOW) en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e9362-127">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9362-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e9362-128">Child Elements</span></span>  

 <span data-ttu-id="e9362-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9362-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9362-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e9362-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e9362-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9362-131">Element</span></span>|<span data-ttu-id="e9362-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9362-132">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="e9362-133">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e9362-133">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="e9362-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9362-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="e9362-135">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-135">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="e9362-136">Use un `<dependentAssembly>` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-136">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="e9362-137">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e9362-137">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9362-138">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9362-138">Remarks</span></span>  

 <span data-ttu-id="e9362-139">Cada **\<dependentAssembly>** elemento debe tener un **\<assemblyIdentity>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="e9362-139">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="e9362-140">Si el `processorArchitecture` atributo está presente, el `<assemblyIdentity>` elemento solo se aplica al ensamblado con la arquitectura de procesador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9362-140">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="e9362-141">Si el `processorArchitecture` atributo no está presente, el `<assemblyIdentity>` elemento se puede aplicar a un ensamblado con cualquier arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="e9362-141">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="e9362-142">En el ejemplo siguiente se muestra un archivo de configuración para dos ensamblados con el mismo nombre que tienen como destino dos arquitecturas de dos procesadores diferentes y cuyas versiones no se han mantenido en la sincronización. Cuando la aplicación se ejecuta en la plataforma x86 `<assemblyIdentity>` , se aplica el primer elemento y se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="e9362-142">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="e9362-143">Si la aplicación se ejecuta en una plataforma distinta de x86 o IA64, ambos se omiten.</span><span class="sxs-lookup"><span data-stu-id="e9362-143">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="e9362-144">Si un archivo de configuración contiene un `<assemblyIdentity>` elemento sin `processorArchitecture` atributo y no contiene un elemento que coincida con la plataforma, se usa el elemento sin el `processorArchitecture` atributo.</span><span class="sxs-lookup"><span data-stu-id="e9362-144">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9362-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9362-145">Example</span></span>  

 <span data-ttu-id="e9362-146">En el ejemplo siguiente se muestra cómo proporcionar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9362-146">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9362-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9362-147">See also</span></span>

- [<span data-ttu-id="e9362-148">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e9362-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9362-149">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e9362-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e9362-150">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="e9362-150">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
