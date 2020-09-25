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
ms.openlocfilehash: b6a39bcecfd2485481677496adcf026d986c283b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170251"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="ace47-102">Elemento \<assemblyBinding> para \<runtime></span><span class="sxs-lookup"><span data-stu-id="ace47-102">\<assemblyBinding> Element for \<runtime></span></span>

<span data-ttu-id="ace47-103">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ace47-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="ace47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ace47-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ace47-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ace47-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ace47-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ace47-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ace47-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ace47-107">Attributes</span></span>  
  
|<span data-ttu-id="ace47-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ace47-108">Attribute</span></span>|<span data-ttu-id="ace47-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ace47-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ace47-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="ace47-110">**xmlns**</span></span>|<span data-ttu-id="ace47-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ace47-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="ace47-112">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ace47-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="ace47-113">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="ace47-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="ace47-114">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="ace47-114">**appliesTo**</span></span>|<span data-ttu-id="ace47-115">Especifica la versión en tiempo de ejecución a la que se aplica la redirección del ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace47-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="ace47-116">Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.</span><span class="sxs-lookup"><span data-stu-id="ace47-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="ace47-117">Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace47-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="ace47-118">El atributo **appliesTo** se incorporó en .NET Framework versión 1,1; se omite en la versión 1,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace47-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="ace47-119">Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="ace47-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ace47-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ace47-120">Child Elements</span></span>  
  
|<span data-ttu-id="ace47-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ace47-121">Element</span></span>|<span data-ttu-id="ace47-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ace47-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="ace47-123">Encapsula la directiva de enlace y la ubicación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ace47-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="ace47-124">Use una **\<dependentAssembly>** etiqueta para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ace47-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="ace47-125">Especifica los subdirectorios en los que busca Common Language Runtime cuando se cargan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ace47-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="ace47-126">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="ace47-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="ace47-127">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="ace47-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ace47-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ace47-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ace47-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="ace47-129">Element</span></span>|<span data-ttu-id="ace47-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="ace47-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ace47-131">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace47-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ace47-132">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ace47-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ace47-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ace47-133">Example</span></span>  

 <span data-ttu-id="ace47-134">En el ejemplo siguiente, se muestra cómo redirigir una versión de ensamblado a otra versión y cómo proporcionar un código base.</span><span class="sxs-lookup"><span data-stu-id="ace47-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="ace47-135">En el ejemplo siguiente se muestra cómo usar el atributo **appliesTo** para redirigir el enlace de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace47-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ace47-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ace47-136">See also</span></span>

- [<span data-ttu-id="ace47-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ace47-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ace47-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ace47-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ace47-139">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="ace47-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
