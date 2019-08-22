---
title: <developmentMode> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7c7f866cdbcd39194d61a3db821bf973b4e057e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663816"
---
# <a name="developmentmode-element"></a><span data-ttu-id="cad8e-102">\<developmentMode >, elemento</span><span class="sxs-lookup"><span data-stu-id="cad8e-102">\<developmentMode> Element</span></span>
<span data-ttu-id="cad8e-103">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="cad8e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cad8e-104">\<configuration></span></span>  
<span data-ttu-id="cad8e-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="cad8e-105">\<runtime></span></span>  
<span data-ttu-id="cad8e-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="cad8e-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad8e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cad8e-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cad8e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cad8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cad8e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cad8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cad8e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cad8e-110">Attributes</span></span>  
  
|<span data-ttu-id="cad8e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="cad8e-111">Attribute</span></span>|<span data-ttu-id="cad8e-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cad8e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cad8e-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="cad8e-113">**developerInstallation**</span></span>|<span data-ttu-id="cad8e-114">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="cad8e-115">Atributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="cad8e-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="cad8e-116">Value</span><span class="sxs-lookup"><span data-stu-id="cad8e-116">Value</span></span>|<span data-ttu-id="cad8e-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cad8e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cad8e-118">**true**</span><span class="sxs-lookup"><span data-stu-id="cad8e-118">**true**</span></span>|<span data-ttu-id="cad8e-119">Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="cad8e-120">**false**</span><span class="sxs-lookup"><span data-stu-id="cad8e-120">**false**</span></span>|<span data-ttu-id="cad8e-121">No busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="cad8e-122">Este es el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="cad8e-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cad8e-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cad8e-123">Child Elements</span></span>  
 <span data-ttu-id="cad8e-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cad8e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cad8e-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cad8e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="cad8e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="cad8e-126">Element</span></span>|<span data-ttu-id="cad8e-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cad8e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cad8e-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cad8e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cad8e-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cad8e-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cad8e-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cad8e-130">Remarks</span></span>  
 <span data-ttu-id="cad8e-131">Use esta configuración solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cad8e-131">Use this setting only at development time.</span></span> <span data-ttu-id="cad8e-132">El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="cad8e-133">Simplemente usa el primer ensamblado que encuentra.</span><span class="sxs-lookup"><span data-stu-id="cad8e-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cad8e-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cad8e-134">Example</span></span>  
 <span data-ttu-id="cad8e-135">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="cad8e-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cad8e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="cad8e-136">See also</span></span>

- [<span data-ttu-id="cad8e-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="cad8e-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cad8e-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cad8e-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cad8e-139">Cómo: Buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="cad8e-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
