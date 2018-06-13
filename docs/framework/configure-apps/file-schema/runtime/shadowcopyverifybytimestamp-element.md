---
title: '&lt;shadowCopyVerifyByTimestamp&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2439a4812163562a73bd3520e65b9973e666a863
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749730"
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a><span data-ttu-id="3c867-102">&lt;shadowCopyVerifyByTimestamp&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="3c867-102">&lt;shadowCopyVerifyByTimestamp&gt; Element</span></span>
<span data-ttu-id="3c867-103">Especifica si la creación de instantáneas usa el comportamiento de inicio predeterminado especificado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o se revierte el comportamiento de inicio de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c867-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3c867-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="3c867-104">\<configuration> Element</span></span>  
<span data-ttu-id="3c867-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="3c867-105">\<runtime> Element</span></span>  
<span data-ttu-id="3c867-106">\<shadowCopyVerifyByTimestamp > elemento</span><span class="sxs-lookup"><span data-stu-id="3c867-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c867-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c867-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c867-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c867-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3c867-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c867-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c867-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c867-110">Attributes</span></span>  
  
|<span data-ttu-id="3c867-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="3c867-111">Attribute</span></span>|<span data-ttu-id="3c867-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c867-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c867-113">enabled</span><span class="sxs-lookup"><span data-stu-id="3c867-113">enabled</span></span>|<span data-ttu-id="3c867-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3c867-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3c867-115">Especifica si los dominios de aplicación que utilizan instantáneas comparan marcas de tiempo de ensamblado al iniciarse, para determinar si un ensamblado se ha actualizado antes de copiar el ensamblado de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="3c867-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3c867-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="3c867-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="3c867-117">Valor</span><span class="sxs-lookup"><span data-stu-id="3c867-117">Value</span></span>|<span data-ttu-id="3c867-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c867-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c867-119">true</span><span class="sxs-lookup"><span data-stu-id="3c867-119">true</span></span>|<span data-ttu-id="3c867-120">Al iniciarse, copia solo los ensamblados que se han actualizado desde la última que se copiaron en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="3c867-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="3c867-121">Este es el valor predeterminado para el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c867-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="3c867-122">False</span><span class="sxs-lookup"><span data-stu-id="3c867-122">false</span></span>|<span data-ttu-id="3c867-123">Revierte el comportamiento de inicio de las versiones anteriores de .NET Framework, que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="3c867-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c867-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c867-124">Child Elements</span></span>  
 <span data-ttu-id="3c867-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c867-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c867-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c867-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3c867-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c867-127">Element</span></span>|<span data-ttu-id="3c867-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c867-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3c867-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c867-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3c867-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3c867-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c867-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c867-131">Remarks</span></span>  
 <span data-ttu-id="3c867-132">A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], los ensamblados son instantáneas sólo si sus marcas de tiempo indican que han cambiado desde la última que se copiaron en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="3c867-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="3c867-133">Esto mejora los tiempos de inicio para muchas aplicaciones que utilizan instantáneas, tal y como se describe en [copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3c867-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="3c867-134">Las aplicaciones que tienen un alto porcentaje y la frecuencia de actualizaciones del ensamblado no pueden beneficiarse de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3c867-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="3c867-135">En ese caso, puede usar este elemento para restaurar el comportamiento de las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c867-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c867-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c867-136">Example</span></span>  
 <span data-ttu-id="3c867-137">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminada de instantáneas en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]y revertir al comportamiento de inicio de las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c867-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c867-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c867-138">See Also</span></span>  
 [<span data-ttu-id="3c867-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3c867-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3c867-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3c867-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3c867-141">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3c867-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
