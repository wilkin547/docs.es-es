---
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 902ed07264615e91721d92861b9d974ea10f0d1e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273889"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="93a90-102">\<shadowCopyVerifyByTimestamp> Element</span><span class="sxs-lookup"><span data-stu-id="93a90-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="93a90-103">Especifica si la creación de instantáneas usa el comportamiento de inicio predeterminado especificado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o se revierte el comportamiento de inicio de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93a90-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="93a90-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="93a90-104">\<configuration> Element</span></span>  
<span data-ttu-id="93a90-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="93a90-105">\<runtime> Element</span></span>  
<span data-ttu-id="93a90-106">\<shadowCopyVerifyByTimestamp> Element</span><span class="sxs-lookup"><span data-stu-id="93a90-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a90-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93a90-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93a90-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93a90-108">Attributes and Elements</span></span>  
 <span data-ttu-id="93a90-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93a90-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93a90-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="93a90-110">Attributes</span></span>  
  
|<span data-ttu-id="93a90-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="93a90-111">Attribute</span></span>|<span data-ttu-id="93a90-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a90-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93a90-113">enabled</span><span class="sxs-lookup"><span data-stu-id="93a90-113">enabled</span></span>|<span data-ttu-id="93a90-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="93a90-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="93a90-115">Especifica si los dominios de aplicación que utilizan instantáneas comparan las marcas de tiempo del ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de la instantánea del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93a90-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="93a90-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="93a90-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="93a90-117">Valor</span><span class="sxs-lookup"><span data-stu-id="93a90-117">Value</span></span>|<span data-ttu-id="93a90-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a90-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93a90-119">true</span><span class="sxs-lookup"><span data-stu-id="93a90-119">true</span></span>|<span data-ttu-id="93a90-120">En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="93a90-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="93a90-121">Este es el valor predeterminado para el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a90-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="93a90-122">False</span><span class="sxs-lookup"><span data-stu-id="93a90-122">false</span></span>|<span data-ttu-id="93a90-123">Revierte el comportamiento de inicio de las versiones anteriores de .NET Framework, lo que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="93a90-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93a90-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93a90-124">Child Elements</span></span>  
 <span data-ttu-id="93a90-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="93a90-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93a90-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93a90-126">Parent Elements</span></span>  
  
|<span data-ttu-id="93a90-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="93a90-127">Element</span></span>|<span data-ttu-id="93a90-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a90-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="93a90-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93a90-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="93a90-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="93a90-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93a90-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93a90-131">Remarks</span></span>  
 <span data-ttu-id="93a90-132">A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], los ensamblados son instantáneas sólo si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="93a90-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="93a90-133">Esto mejora los tiempos de inicio para muchas aplicaciones que utilizan instantáneas, como se describe en [copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="93a90-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="93a90-134">Las aplicaciones que tienen un alto porcentaje y una frecuencia de actualizaciones del ensamblado no pueden beneficiarse de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="93a90-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="93a90-135">En ese caso, puede usar este elemento para restaurar el comportamiento de las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93a90-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93a90-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93a90-136">Example</span></span>  
 <span data-ttu-id="93a90-137">El ejemplo siguiente muestra cómo deshabilitar el comportamiento de inicio predeterminado de las instantáneas en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]y revertir al comportamiento de inicio de las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93a90-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93a90-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="93a90-138">See also</span></span>
- [<span data-ttu-id="93a90-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="93a90-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="93a90-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="93a90-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="93a90-141">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="93a90-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
