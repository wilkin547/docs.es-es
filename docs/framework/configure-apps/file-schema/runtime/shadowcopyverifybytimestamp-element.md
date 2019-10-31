---
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115726"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="0810b-102">Elemento \<shadowCopyVerifyByTimestamp></span><span class="sxs-lookup"><span data-stu-id="0810b-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="0810b-103">Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0810b-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
<span data-ttu-id="0810b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0810b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0810b-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0810b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0810b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<shadowCopyVerifyByTimestamp >**</span><span class="sxs-lookup"><span data-stu-id="0810b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0810b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0810b-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0810b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0810b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0810b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0810b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0810b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0810b-110">Attributes</span></span>  
  
|<span data-ttu-id="0810b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0810b-111">Attribute</span></span>|<span data-ttu-id="0810b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0810b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0810b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="0810b-113">enabled</span></span>|<span data-ttu-id="0810b-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0810b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="0810b-115">Especifica si los dominios de aplicación que usan la copia sombra comparan las marcas de tiempo de ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de copiar las instantáneas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0810b-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0810b-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="0810b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="0810b-117">Valor</span><span class="sxs-lookup"><span data-stu-id="0810b-117">Value</span></span>|<span data-ttu-id="0810b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0810b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0810b-119">true</span><span class="sxs-lookup"><span data-stu-id="0810b-119">true</span></span>|<span data-ttu-id="0810b-120">En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="0810b-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="0810b-121">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0810b-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="0810b-122">False</span><span class="sxs-lookup"><span data-stu-id="0810b-122">false</span></span>|<span data-ttu-id="0810b-123">Revierte al comportamiento de inicio de las versiones anteriores del .NET Framework, que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="0810b-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0810b-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0810b-124">Child Elements</span></span>  
 <span data-ttu-id="0810b-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0810b-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0810b-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0810b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0810b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="0810b-127">Element</span></span>|<span data-ttu-id="0810b-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="0810b-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0810b-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0810b-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0810b-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0810b-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0810b-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0810b-131">Remarks</span></span>  
 <span data-ttu-id="0810b-132">A partir de la .NET Framework 4, los ensamblados solo se copian con instantáneas si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="0810b-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="0810b-133">Esto mejora los tiempos de inicio de muchas aplicaciones que usan la copia sombra, como se describe en [instantáneas de copia de ensamblados](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="0810b-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="0810b-134">Es posible que las aplicaciones que tienen un alto porcentaje y la frecuencia de las actualizaciones del ensamblado no se beneficien de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="0810b-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="0810b-135">En ese caso, puede usar este elemento para restaurar el comportamiento de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0810b-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0810b-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0810b-136">Example</span></span>  
 <span data-ttu-id="0810b-137">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminado de la copia sombra en el .NET Framework 4 y cómo revertir al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0810b-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0810b-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="0810b-138">See also</span></span>

- [<span data-ttu-id="0810b-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0810b-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0810b-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0810b-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0810b-141">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0810b-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
