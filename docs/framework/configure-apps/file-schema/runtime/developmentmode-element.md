---
title: '&lt;developmentMode&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4573c3a5e0cf64996f2a4e109736d966b754494a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltdevelopmentmodegt-element"></a><span data-ttu-id="45ef1-102">&lt;developmentMode&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="45ef1-102">&lt;developmentMode&gt; Element</span></span>
<span data-ttu-id="45ef1-103">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="45ef1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="45ef1-104">\<configuration></span></span>  
<span data-ttu-id="45ef1-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="45ef1-105">\<runtime></span></span>  
<span data-ttu-id="45ef1-106">\<developmentMode ></span><span class="sxs-lookup"><span data-stu-id="45ef1-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ef1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45ef1-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45ef1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="45ef1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="45ef1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="45ef1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45ef1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="45ef1-110">Attributes</span></span>  
  
|<span data-ttu-id="45ef1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="45ef1-111">Attribute</span></span>|<span data-ttu-id="45ef1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="45ef1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45ef1-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="45ef1-113">**developerInstallation**</span></span>|<span data-ttu-id="45ef1-114">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="45ef1-115">Atributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="45ef1-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="45ef1-116">Valor</span><span class="sxs-lookup"><span data-stu-id="45ef1-116">Value</span></span>|<span data-ttu-id="45ef1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="45ef1-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45ef1-118">**true**</span><span class="sxs-lookup"><span data-stu-id="45ef1-118">**true**</span></span>|<span data-ttu-id="45ef1-119">Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="45ef1-120">**false**</span><span class="sxs-lookup"><span data-stu-id="45ef1-120">**false**</span></span>|<span data-ttu-id="45ef1-121">No buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="45ef1-122">Este es el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="45ef1-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45ef1-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="45ef1-123">Child Elements</span></span>  
 <span data-ttu-id="45ef1-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="45ef1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45ef1-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="45ef1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="45ef1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="45ef1-126">Element</span></span>|<span data-ttu-id="45ef1-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="45ef1-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="45ef1-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45ef1-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="45ef1-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="45ef1-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45ef1-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45ef1-130">Remarks</span></span>  
 <span data-ttu-id="45ef1-131">Use esta opción solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="45ef1-131">Use this setting only at development time.</span></span> <span data-ttu-id="45ef1-132">El tiempo de ejecución no comprueba las versiones de ensamblados con nombre seguro que se encuentran en la variable DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="45ef1-133">Simplemente utiliza el primer ensamblado que encuentre.</span><span class="sxs-lookup"><span data-stu-id="45ef1-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45ef1-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45ef1-134">Example</span></span>  
 <span data-ttu-id="45ef1-135">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="45ef1-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45ef1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="45ef1-136">See Also</span></span>  
 [<span data-ttu-id="45ef1-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="45ef1-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="45ef1-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="45ef1-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="45ef1-139">Cómo: Buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="45ef1-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
