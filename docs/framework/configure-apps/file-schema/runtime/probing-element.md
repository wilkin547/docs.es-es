---
title: '&lt;el sondeo&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cab16e83466b5954bfebac07dd79c9a8b5e4594
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="c359c-102">&lt;el sondeo&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="c359c-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="c359c-103">Especifica los subdirectorios base de common language runtime buscar al cargar los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c359c-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="c359c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c359c-104">\<configuration></span></span>  
<span data-ttu-id="c359c-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="c359c-105">\<runtime></span></span>  
<span data-ttu-id="c359c-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="c359c-106">\<assemblyBinding></span></span>  
<span data-ttu-id="c359c-107">\<probing ></span><span class="sxs-lookup"><span data-stu-id="c359c-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c359c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c359c-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c359c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c359c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c359c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c359c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c359c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c359c-111">Attributes</span></span>  
  
|<span data-ttu-id="c359c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c359c-112">Attribute</span></span>|<span data-ttu-id="c359c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c359c-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="c359c-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c359c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c359c-115">Especifica los subdirectorios del directorio base de la aplicación que pueden contener ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c359c-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="c359c-116">Delimita cada subdirectorio con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c359c-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c359c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c359c-117">Child Elements</span></span>  
 <span data-ttu-id="c359c-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c359c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c359c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c359c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c359c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c359c-120">Element</span></span>|<span data-ttu-id="c359c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c359c-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c359c-122">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c359c-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c359c-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c359c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c359c-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c359c-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c359c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c359c-125">Example</span></span>  
 <span data-ttu-id="c359c-126">En el ejemplo siguiente se muestra cómo especificar los subdirectorios base de la aplicación que el tiempo de ejecución debe buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c359c-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c359c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c359c-127">See Also</span></span>  
 [<span data-ttu-id="c359c-128">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c359c-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="c359c-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c359c-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="c359c-130">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="c359c-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="c359c-131">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="c359c-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
