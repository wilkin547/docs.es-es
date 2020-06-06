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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154210"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="9594c-102">\<dependentAssembly> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9594c-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="9594c-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9594c-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="9594c-104">Use un `dependentAssembly` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9594c-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="9594c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9594c-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9594c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9594c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="9594c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9594c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9594c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9594c-108">Attributes</span></span>  
 <span data-ttu-id="9594c-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9594c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9594c-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9594c-110">Child Elements</span></span>  
  
|<span data-ttu-id="9594c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9594c-111">Element</span></span>|<span data-ttu-id="9594c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9594c-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="9594c-113">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9594c-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="9594c-114">Este elemento debe estar incluido en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="9594c-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="9594c-115">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9594c-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="9594c-116">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="9594c-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="9594c-117">Especifica si el tiempo de ejecución aplica la Directiva de edición para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9594c-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9594c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9594c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9594c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9594c-119">Element</span></span>|<span data-ttu-id="9594c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9594c-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="9594c-121">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9594c-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="9594c-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9594c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9594c-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9594c-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9594c-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9594c-124">Example</span></span>  
 <span data-ttu-id="9594c-125">En el ejemplo siguiente se muestra cómo encapsular la información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9594c-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9594c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9594c-126">See also</span></span>

- [<span data-ttu-id="9594c-127">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="9594c-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9594c-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9594c-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9594c-129">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="9594c-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
