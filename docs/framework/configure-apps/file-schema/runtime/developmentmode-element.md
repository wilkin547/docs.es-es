---
description: 'Más información acerca de: <developmentMode> elemento'
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
ms.openlocfilehash: 668461d13c8a1767268692804e9783bb6d4b9a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787128"
---
# <a name="developmentmode-element"></a><span data-ttu-id="fbee1-103">\<developmentMode> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="fbee1-103">\<developmentMode> Element</span></span>

<span data-ttu-id="fbee1-104">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-104">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="fbee1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbee1-105">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbee1-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fbee1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fbee1-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fbee1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbee1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fbee1-108">Attributes</span></span>  
  
|<span data-ttu-id="fbee1-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="fbee1-109">Attribute</span></span>|<span data-ttu-id="fbee1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbee1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbee1-111">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="fbee1-111">**developerInstallation**</span></span>|<span data-ttu-id="fbee1-112">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-112">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="fbee1-113">Atributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="fbee1-113">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="fbee1-114">Value</span><span class="sxs-lookup"><span data-stu-id="fbee1-114">Value</span></span>|<span data-ttu-id="fbee1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbee1-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbee1-116">**true**</span><span class="sxs-lookup"><span data-stu-id="fbee1-116">**true**</span></span>|<span data-ttu-id="fbee1-117">Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-117">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="fbee1-118">**false**</span><span class="sxs-lookup"><span data-stu-id="fbee1-118">**false**</span></span>|<span data-ttu-id="fbee1-119">No busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-119">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="fbee1-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fbee1-120">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbee1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fbee1-121">Child Elements</span></span>  

 <span data-ttu-id="fbee1-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fbee1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbee1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fbee1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fbee1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbee1-124">Element</span></span>|<span data-ttu-id="fbee1-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbee1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fbee1-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbee1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fbee1-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fbee1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbee1-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fbee1-128">Remarks</span></span>  

 <span data-ttu-id="fbee1-129">Use esta configuración solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fbee1-129">Use this setting only at development time.</span></span> <span data-ttu-id="fbee1-130">El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-130">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="fbee1-131">Simplemente usa el primer ensamblado que encuentra.</span><span class="sxs-lookup"><span data-stu-id="fbee1-131">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbee1-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbee1-132">Example</span></span>  

 <span data-ttu-id="fbee1-133">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="fbee1-133">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbee1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbee1-134">See also</span></span>

- [<span data-ttu-id="fbee1-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fbee1-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fbee1-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fbee1-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fbee1-137">Procedimiento para buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="fbee1-137">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
