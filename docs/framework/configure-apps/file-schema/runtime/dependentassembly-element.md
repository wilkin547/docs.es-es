---
description: 'Más información acerca de: <dependentAssembly> elemento'
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
ms.openlocfilehash: c804920de961fc609fd04a0853ecbdbc9202e5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719089"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="db5e7-103">\<dependentAssembly> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="db5e7-103">\<dependentAssembly> Element</span></span>

<span data-ttu-id="db5e7-104">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db5e7-104">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="db5e7-105">Use un `dependentAssembly` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db5e7-105">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="db5e7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db5e7-106">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db5e7-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db5e7-107">Attributes and Elements</span></span>  

 <span data-ttu-id="db5e7-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="db5e7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db5e7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="db5e7-109">Attributes</span></span>  

 <span data-ttu-id="db5e7-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="db5e7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="db5e7-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db5e7-111">Child Elements</span></span>  
  
|<span data-ttu-id="db5e7-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="db5e7-112">Element</span></span>|<span data-ttu-id="db5e7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="db5e7-113">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="db5e7-114">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db5e7-114">Contains identifying information about the assembly.</span></span> <span data-ttu-id="db5e7-115">Este elemento debe estar incluido en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="db5e7-115">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="db5e7-116">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="db5e7-116">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="db5e7-117">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="db5e7-117">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="db5e7-118">Especifica si el tiempo de ejecución aplica la Directiva de edición para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db5e7-118">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db5e7-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db5e7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="db5e7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="db5e7-120">Element</span></span>|<span data-ttu-id="db5e7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="db5e7-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="db5e7-122">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="db5e7-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="db5e7-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db5e7-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="db5e7-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="db5e7-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="db5e7-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db5e7-125">Example</span></span>  

 <span data-ttu-id="db5e7-126">En el ejemplo siguiente se muestra cómo encapsular la información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="db5e7-126">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="db5e7-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="db5e7-127">See also</span></span>

- [<span data-ttu-id="db5e7-128">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="db5e7-128">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="db5e7-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="db5e7-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="db5e7-130">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="db5e7-130">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
