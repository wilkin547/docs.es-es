---
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115726"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="22718-102">\<shadowCopyVerifyByTimestamp> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="22718-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="22718-103">Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22718-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="22718-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22718-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22718-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22718-105">Attributes and Elements</span></span>  
 <span data-ttu-id="22718-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22718-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22718-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="22718-107">Attributes</span></span>  
  
|<span data-ttu-id="22718-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="22718-108">Attribute</span></span>|<span data-ttu-id="22718-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="22718-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22718-110">enabled</span><span class="sxs-lookup"><span data-stu-id="22718-110">enabled</span></span>|<span data-ttu-id="22718-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="22718-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="22718-112">Especifica si los dominios de aplicación que usan la copia sombra comparan las marcas de tiempo de ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de copiar las instantáneas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22718-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="22718-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="22718-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="22718-114">Value</span><span class="sxs-lookup"><span data-stu-id="22718-114">Value</span></span>|<span data-ttu-id="22718-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="22718-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22718-116">true</span><span class="sxs-lookup"><span data-stu-id="22718-116">true</span></span>|<span data-ttu-id="22718-117">En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="22718-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="22718-118">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="22718-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="22718-119">false</span><span class="sxs-lookup"><span data-stu-id="22718-119">false</span></span>|<span data-ttu-id="22718-120">Revierte al comportamiento de inicio de las versiones anteriores del .NET Framework, que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="22718-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22718-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22718-121">Child Elements</span></span>  
 <span data-ttu-id="22718-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22718-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22718-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22718-123">Parent Elements</span></span>  
  
|<span data-ttu-id="22718-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="22718-124">Element</span></span>|<span data-ttu-id="22718-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="22718-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22718-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22718-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="22718-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="22718-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22718-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22718-128">Remarks</span></span>  
 <span data-ttu-id="22718-129">A partir de la .NET Framework 4, los ensamblados solo se copian con instantáneas si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="22718-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="22718-130">Esto mejora los tiempos de inicio de muchas aplicaciones que usan la copia sombra, como se describe en [instantáneas de copia de ensamblados](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="22718-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="22718-131">Es posible que las aplicaciones que tienen un alto porcentaje y la frecuencia de las actualizaciones del ensamblado no se beneficien de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="22718-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="22718-132">En ese caso, puede usar este elemento para restaurar el comportamiento de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22718-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22718-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22718-133">Example</span></span>  
 <span data-ttu-id="22718-134">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminado de la copia sombra en el .NET Framework 4 y cómo revertir al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22718-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22718-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22718-135">See also</span></span>

- [<span data-ttu-id="22718-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="22718-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="22718-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="22718-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="22718-138">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="22718-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
