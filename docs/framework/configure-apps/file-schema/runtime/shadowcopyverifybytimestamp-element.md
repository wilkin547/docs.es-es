---
description: 'Más información acerca de: <shadowCopyVerifyByTimestamp> elemento'
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 273bf4c5b01b300cfd564de4ee29c402c6f3e7ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740098"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="6ae83-103">\<shadowCopyVerifyByTimestamp> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="6ae83-103">\<shadowCopyVerifyByTimestamp> Element</span></span>

<span data-ttu-id="6ae83-104">Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ae83-104">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="6ae83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ae83-105">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ae83-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ae83-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6ae83-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ae83-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ae83-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ae83-108">Attributes</span></span>  
  
|<span data-ttu-id="6ae83-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ae83-109">Attribute</span></span>|<span data-ttu-id="6ae83-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ae83-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ae83-111">enabled</span><span class="sxs-lookup"><span data-stu-id="6ae83-111">enabled</span></span>|<span data-ttu-id="6ae83-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6ae83-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="6ae83-113">Especifica si los dominios de aplicación que usan la copia sombra comparan las marcas de tiempo de ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de copiar las instantáneas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ae83-113">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6ae83-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="6ae83-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="6ae83-115">Value</span><span class="sxs-lookup"><span data-stu-id="6ae83-115">Value</span></span>|<span data-ttu-id="6ae83-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ae83-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6ae83-117">true</span><span class="sxs-lookup"><span data-stu-id="6ae83-117">true</span></span>|<span data-ttu-id="6ae83-118">En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="6ae83-118">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="6ae83-119">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6ae83-119">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="6ae83-120">false</span><span class="sxs-lookup"><span data-stu-id="6ae83-120">false</span></span>|<span data-ttu-id="6ae83-121">Revierte al comportamiento de inicio de las versiones anteriores del .NET Framework, que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="6ae83-121">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ae83-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ae83-122">Child Elements</span></span>  

 <span data-ttu-id="6ae83-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ae83-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ae83-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ae83-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6ae83-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ae83-125">Element</span></span>|<span data-ttu-id="6ae83-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ae83-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6ae83-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ae83-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6ae83-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6ae83-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ae83-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ae83-129">Remarks</span></span>  

 <span data-ttu-id="6ae83-130">A partir de la .NET Framework 4, los ensamblados solo se copian con instantáneas si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="6ae83-130">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="6ae83-131">Esto mejora los tiempos de inicio de muchas aplicaciones que usan la copia sombra, como se describe en [instantáneas de copia de ensamblados](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="6ae83-131">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="6ae83-132">Es posible que las aplicaciones que tienen un alto porcentaje y la frecuencia de las actualizaciones del ensamblado no se beneficien de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6ae83-132">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="6ae83-133">En ese caso, puede usar este elemento para restaurar el comportamiento de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ae83-133">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae83-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ae83-134">Example</span></span>  

 <span data-ttu-id="6ae83-135">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminado de la copia sombra en el .NET Framework 4 y cómo revertir al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ae83-135">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ae83-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ae83-136">See also</span></span>

- [<span data-ttu-id="6ae83-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6ae83-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6ae83-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6ae83-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6ae83-139">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="6ae83-139">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
