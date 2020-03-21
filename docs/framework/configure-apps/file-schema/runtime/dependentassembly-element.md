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
ms.openlocfilehash: 2de8c752867d00708173d11d1851f415a2e8518d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154210"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="10027-102">\<dependentAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="10027-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="10027-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="10027-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="10027-104">Utilice `dependentAssembly` un elemento para cada ensamblaje.</span><span class="sxs-lookup"><span data-stu-id="10027-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="10027-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="10027-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="10027-106">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="10027-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="10027-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="10027-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="10027-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependienteEnsamblaje>**</span><span class="sxs-lookup"><span data-stu-id="10027-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10027-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10027-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10027-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10027-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10027-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10027-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10027-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="10027-112">Attributes</span></span>  
 <span data-ttu-id="10027-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="10027-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10027-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10027-114">Child Elements</span></span>  
  
|<span data-ttu-id="10027-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="10027-115">Element</span></span>|<span data-ttu-id="10027-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="10027-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="10027-117">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="10027-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="10027-118">Este elemento debe incluirse en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="10027-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="10027-119">Especifica dónde el tiempo de ejecución puede encontrar un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="10027-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="10027-120">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="10027-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="10027-121">Especifica si el tiempo de ejecución aplica la directiva de publicador para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="10027-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10027-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10027-122">Parent Elements</span></span>  
  
|<span data-ttu-id="10027-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="10027-123">Element</span></span>|<span data-ttu-id="10027-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="10027-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="10027-125">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="10027-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="10027-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10027-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10027-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10027-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10027-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10027-128">Example</span></span>  
 <span data-ttu-id="10027-129">En el ejemplo siguiente se muestra cómo encapsular información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="10027-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10027-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10027-130">See also</span></span>

- [<span data-ttu-id="10027-131">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="10027-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="10027-132">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="10027-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="10027-133">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="10027-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
