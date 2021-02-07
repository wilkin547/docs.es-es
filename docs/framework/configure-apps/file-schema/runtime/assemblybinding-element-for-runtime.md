---
description: 'Más información sobre: <assemblyBinding> elemento para <runtime>'
title: Elemento <assemblyBinding> para <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: a797b541f9f13852234872f1eb2fc68a2eac727d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719232"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="149a9-103">Elemento \<assemblyBinding> para \<runtime></span><span class="sxs-lookup"><span data-stu-id="149a9-103">\<assemblyBinding> Element for \<runtime></span></span>

<span data-ttu-id="149a9-104">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="149a9-104">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="149a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="149a9-105">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="149a9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="149a9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="149a9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="149a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="149a9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="149a9-108">Attributes</span></span>  
  
|<span data-ttu-id="149a9-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="149a9-109">Attribute</span></span>|<span data-ttu-id="149a9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="149a9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="149a9-111">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="149a9-111">**xmlns**</span></span>|<span data-ttu-id="149a9-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="149a9-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="149a9-113">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="149a9-113">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="149a9-114">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="149a9-114">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="149a9-115">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="149a9-115">**appliesTo**</span></span>|<span data-ttu-id="149a9-116">Especifica la versión en tiempo de ejecución a la que se aplica la redirección del ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="149a9-116">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="149a9-117">Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.</span><span class="sxs-lookup"><span data-stu-id="149a9-117">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="149a9-118">Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="149a9-118">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="149a9-119">El atributo **appliesTo** se incorporó en .NET Framework versión 1,1; se omite en la versión 1,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="149a9-119">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="149a9-120">Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="149a9-120">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="149a9-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="149a9-121">Child Elements</span></span>  
  
|<span data-ttu-id="149a9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="149a9-122">Element</span></span>|<span data-ttu-id="149a9-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="149a9-123">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="149a9-124">Encapsula la directiva de enlace y la ubicación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="149a9-124">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="149a9-125">Use una **\<dependentAssembly>** etiqueta para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="149a9-125">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="149a9-126">Especifica los subdirectorios en los que busca Common Language Runtime cuando se cargan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="149a9-126">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="149a9-127">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="149a9-127">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="149a9-128">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="149a9-128">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="149a9-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="149a9-129">Parent Elements</span></span>  
  
|<span data-ttu-id="149a9-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="149a9-130">Element</span></span>|<span data-ttu-id="149a9-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="149a9-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="149a9-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="149a9-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="149a9-133">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="149a9-133">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="149a9-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="149a9-134">Example</span></span>  

 <span data-ttu-id="149a9-135">En el ejemplo siguiente, se muestra cómo redirigir una versión de ensamblado a otra versión y cómo proporcionar un código base.</span><span class="sxs-lookup"><span data-stu-id="149a9-135">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="149a9-136">En el ejemplo siguiente se muestra cómo usar el atributo **appliesTo** para redirigir el enlace de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="149a9-136">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="149a9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="149a9-137">See also</span></span>

- [<span data-ttu-id="149a9-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="149a9-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="149a9-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="149a9-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="149a9-140">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="149a9-140">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
