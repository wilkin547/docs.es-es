---
title: Elemento <assemblyBinding> para <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: c688353583f5e452950d63b7d02c48505b6ae999
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118130"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="51c44-102">\<elemento de > assemblyBinding para \<Runtime ></span><span class="sxs-lookup"><span data-stu-id="51c44-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="51c44-103">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="51c44-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
<span data-ttu-id="51c44-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="51c44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="51c44-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="51c44-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="51c44-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="51c44-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c44-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51c44-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51c44-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="51c44-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51c44-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="51c44-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51c44-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="51c44-110">Attributes</span></span>  
  
|<span data-ttu-id="51c44-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="51c44-111">Attribute</span></span>|<span data-ttu-id="51c44-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="51c44-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51c44-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="51c44-113">**xmlns**</span></span>|<span data-ttu-id="51c44-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="51c44-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="51c44-115">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="51c44-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="51c44-116">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="51c44-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="51c44-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="51c44-117">**appliesTo**</span></span>|<span data-ttu-id="51c44-118">Especifica la versión en tiempo de ejecución a la que se aplica la redirección del ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c44-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="51c44-119">Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.</span><span class="sxs-lookup"><span data-stu-id="51c44-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="51c44-120">Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c44-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="51c44-121">El atributo **appliesTo** se incorporó en .NET Framework versión 1,1; se omite en la versión 1,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c44-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="51c44-122">Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="51c44-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51c44-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="51c44-123">Child Elements</span></span>  
  
|<span data-ttu-id="51c44-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="51c44-124">Element</span></span>|<span data-ttu-id="51c44-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="51c44-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51c44-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="51c44-126">\<dependentAssembly></span></span>](dependentassembly-element.md)|<span data-ttu-id="51c44-127">Encapsula la directiva de enlace y la ubicación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="51c44-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="51c44-128">Use una\<la etiqueta de **> dependentAssembly** para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="51c44-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="51c44-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="51c44-129">\<probing></span></span>](probing-element.md)|<span data-ttu-id="51c44-130">Especifica los subdirectorios en los que busca Common Language Runtime cuando se cargan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="51c44-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="51c44-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="51c44-131">\<publisherPolicy></span></span>](publisherpolicy-element.md)|<span data-ttu-id="51c44-132">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="51c44-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="51c44-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="51c44-133">\<qualifyAssembly></span></span>](qualifyassembly-element.md)|<span data-ttu-id="51c44-134">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="51c44-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51c44-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="51c44-135">Parent Elements</span></span>  
  
|<span data-ttu-id="51c44-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="51c44-136">Element</span></span>|<span data-ttu-id="51c44-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="51c44-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="51c44-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c44-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="51c44-139">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="51c44-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51c44-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51c44-140">Example</span></span>  
 <span data-ttu-id="51c44-141">En el ejemplo siguiente, se muestra cómo redirigir una versión de ensamblado a otra versión y cómo proporcionar un código base.</span><span class="sxs-lookup"><span data-stu-id="51c44-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="51c44-142">En el ejemplo siguiente se muestra cómo usar el atributo **appliesTo** para redirigir el enlace de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c44-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51c44-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="51c44-143">See also</span></span>

- [<span data-ttu-id="51c44-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="51c44-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="51c44-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="51c44-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="51c44-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="51c44-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
