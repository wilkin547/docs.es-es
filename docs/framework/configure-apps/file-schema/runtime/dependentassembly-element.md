---
title: <dependentAssembly> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1ee9c3c19c0a3e86b6761f95ccab0292b5e15c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273954"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="d0f8d-102">\<dependentAssembly > elemento</span><span class="sxs-lookup"><span data-stu-id="d0f8d-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="d0f8d-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="d0f8d-104">Utilice uno `dependentAssembly` (elemento) para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="d0f8d-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d0f8d-105">\<configuration></span></span>  
<span data-ttu-id="d0f8d-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d0f8d-106">\<runtime></span></span>  
<span data-ttu-id="d0f8d-107">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="d0f8d-107">\<assemblyBinding></span></span>  
<span data-ttu-id="d0f8d-108">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="d0f8d-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f8d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0f8d-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0f8d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0f8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d0f8d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0f8d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0f8d-112">Attributes</span></span>  
 <span data-ttu-id="d0f8d-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0f8d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0f8d-114">Child Elements</span></span>  
  
|<span data-ttu-id="d0f8d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0f8d-115">Element</span></span>|<span data-ttu-id="d0f8d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0f8d-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="d0f8d-117">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="d0f8d-118">Este elemento debe incluirse en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="d0f8d-119">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="d0f8d-120">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="d0f8d-121">Especifica si el tiempo de ejecución aplica la directiva de publicador para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0f8d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0f8d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d0f8d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0f8d-123">Element</span></span>|<span data-ttu-id="d0f8d-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0f8d-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="d0f8d-125">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="d0f8d-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d0f8d-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0f8d-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0f8d-128">Example</span></span>  
 <span data-ttu-id="d0f8d-129">El ejemplo siguiente muestra cómo encapsular la información de dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d0f8d-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0f8d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0f8d-130">See also</span></span>
- [<span data-ttu-id="d0f8d-131">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d0f8d-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d0f8d-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d0f8d-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d0f8d-133">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="d0f8d-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
