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
ms.openlocfilehash: 33309ed89b4d31580da5de3aeb38e9e1fd8ae4d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117595"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="00b3b-102">\<elemento > dependentAssembly</span><span class="sxs-lookup"><span data-stu-id="00b3b-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="00b3b-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="00b3b-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="00b3b-104">Use un elemento `dependentAssembly` para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="00b3b-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="00b3b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00b3b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00b3b-106">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="00b3b-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="00b3b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="00b3b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="00b3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**dependentAssembly >**</span><span class="sxs-lookup"><span data-stu-id="00b3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b3b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00b3b-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00b3b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00b3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="00b3b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00b3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00b3b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="00b3b-112">Attributes</span></span>  
 <span data-ttu-id="00b3b-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00b3b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00b3b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00b3b-114">Child Elements</span></span>  
  
|<span data-ttu-id="00b3b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b3b-115">Element</span></span>|<span data-ttu-id="00b3b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="00b3b-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="00b3b-117">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="00b3b-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="00b3b-118">Este elemento debe estar incluido en cada elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="00b3b-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="00b3b-119">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="00b3b-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="00b3b-120">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="00b3b-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="00b3b-121">Especifica si el tiempo de ejecución aplica la Directiva de edición para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="00b3b-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00b3b-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00b3b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="00b3b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b3b-123">Element</span></span>|<span data-ttu-id="00b3b-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="00b3b-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="00b3b-125">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="00b3b-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="00b3b-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00b3b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="00b3b-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00b3b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00b3b-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00b3b-128">Example</span></span>  
 <span data-ttu-id="00b3b-129">En el ejemplo siguiente se muestra cómo encapsular la información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="00b3b-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00b3b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="00b3b-130">See also</span></span>

- [<span data-ttu-id="00b3b-131">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="00b3b-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00b3b-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="00b3b-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="00b3b-133">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="00b3b-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
