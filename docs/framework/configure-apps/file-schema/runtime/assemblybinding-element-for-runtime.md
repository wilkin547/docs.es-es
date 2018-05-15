---
title: '&lt;assemblyBinding&gt; (elemento) para &lt;en tiempo de ejecución&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d84c134b8e2b048f39836bbc10af06039e96719e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltassemblybindinggt-element-for-ltruntimegt"></a><span data-ttu-id="0b87b-102">&lt;assemblyBinding&gt; (elemento) para &lt;en tiempo de ejecución&gt;</span><span class="sxs-lookup"><span data-stu-id="0b87b-102">&lt;assemblyBinding&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="0b87b-103">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0b87b-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="0b87b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0b87b-104">\<configuration></span></span>  
<span data-ttu-id="0b87b-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="0b87b-105">\<runtime></span></span>  
<span data-ttu-id="0b87b-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="0b87b-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b87b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b87b-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b87b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0b87b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0b87b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0b87b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b87b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b87b-110">Attributes</span></span>  
  
|<span data-ttu-id="0b87b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0b87b-111">Attribute</span></span>|<span data-ttu-id="0b87b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b87b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b87b-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="0b87b-113">**xmlns**</span></span>|<span data-ttu-id="0b87b-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0b87b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="0b87b-115">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0b87b-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="0b87b-116">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="0b87b-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="0b87b-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="0b87b-117">**appliesTo**</span></span>|<span data-ttu-id="0b87b-118">Especifica la versión en tiempo de ejecución a la que se aplica la redirección del ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b87b-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="0b87b-119">Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.</span><span class="sxs-lookup"><span data-stu-id="0b87b-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="0b87b-120">Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b87b-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="0b87b-121">El **appliesTo** atributo se introdujo en .NET Framework versión 1.1; se omite la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b87b-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="0b87b-122">Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="0b87b-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b87b-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0b87b-123">Child Elements</span></span>  
  
|<span data-ttu-id="0b87b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b87b-124">Element</span></span>|<span data-ttu-id="0b87b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b87b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b87b-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="0b87b-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="0b87b-127">Encapsula la directiva de enlace y la ubicación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0b87b-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="0b87b-128">Use una  **\<dependentAssembly >** etiqueta para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0b87b-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="0b87b-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="0b87b-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="0b87b-130">Especifica los subdirectorios en los que busca Common Language Runtime cuando se cargan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0b87b-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="0b87b-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="0b87b-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="0b87b-132">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="0b87b-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="0b87b-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="0b87b-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="0b87b-134">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="0b87b-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b87b-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0b87b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0b87b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b87b-136">Element</span></span>|<span data-ttu-id="0b87b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b87b-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0b87b-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b87b-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0b87b-139">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0b87b-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b87b-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b87b-140">Example</span></span>  
 <span data-ttu-id="0b87b-141">En el ejemplo siguiente, se muestra cómo redirigir una versión de ensamblado a otra versión y cómo proporcionar un código base.</span><span class="sxs-lookup"><span data-stu-id="0b87b-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="0b87b-142">En el ejemplo siguiente se muestra cómo utilizar el **appliesTo** atributo para redirigir el enlace de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b87b-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b87b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b87b-143">See Also</span></span>  
 [<span data-ttu-id="0b87b-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0b87b-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="0b87b-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0b87b-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="0b87b-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="0b87b-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
