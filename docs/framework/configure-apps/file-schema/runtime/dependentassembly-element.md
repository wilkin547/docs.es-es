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
ms.openlocfilehash: 6a924b1998651c923c64429029a118dd1e9ede69
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199008"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="bb185-102">\<dependentAssembly> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="bb185-102">\<dependentAssembly> Element</span></span>

<span data-ttu-id="bb185-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb185-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="bb185-104">Use un `dependentAssembly` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb185-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="bb185-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb185-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb185-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bb185-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bb185-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bb185-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb185-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb185-108">Attributes</span></span>  

 <span data-ttu-id="bb185-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bb185-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb185-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bb185-110">Child Elements</span></span>  
  
|<span data-ttu-id="bb185-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb185-111">Element</span></span>|<span data-ttu-id="bb185-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb185-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="bb185-113">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb185-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="bb185-114">Este elemento debe estar incluido en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="bb185-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="bb185-115">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="bb185-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="bb185-116">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="bb185-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="bb185-117">Especifica si el tiempo de ejecución aplica la Directiva de edición para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb185-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb185-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bb185-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bb185-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb185-119">Element</span></span>|<span data-ttu-id="bb185-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb185-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="bb185-121">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bb185-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="bb185-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb185-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb185-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bb185-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb185-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb185-124">Example</span></span>  

 <span data-ttu-id="bb185-125">En el ejemplo siguiente se muestra cómo encapsular la información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bb185-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb185-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb185-126">See also</span></span>

- [<span data-ttu-id="bb185-127">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bb185-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb185-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bb185-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb185-129">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="bb185-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
