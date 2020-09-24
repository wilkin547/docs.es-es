---
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: c0dc190e69ca9650d518ee297b12f79f8c47d58b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183980"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="f11c2-102">\<shadowCopyVerifyByTimestamp> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="f11c2-102">\<shadowCopyVerifyByTimestamp> Element</span></span>

<span data-ttu-id="f11c2-103">Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11c2-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="f11c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f11c2-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f11c2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f11c2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f11c2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f11c2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f11c2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f11c2-107">Attributes</span></span>  
  
|<span data-ttu-id="f11c2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f11c2-108">Attribute</span></span>|<span data-ttu-id="f11c2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f11c2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f11c2-110">enabled</span><span class="sxs-lookup"><span data-stu-id="f11c2-110">enabled</span></span>|<span data-ttu-id="f11c2-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f11c2-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f11c2-112">Especifica si los dominios de aplicación que usan la copia sombra comparan las marcas de tiempo de ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de copiar las instantáneas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f11c2-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f11c2-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="f11c2-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="f11c2-114">Value</span><span class="sxs-lookup"><span data-stu-id="f11c2-114">Value</span></span>|<span data-ttu-id="f11c2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f11c2-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f11c2-116">true</span><span class="sxs-lookup"><span data-stu-id="f11c2-116">true</span></span>|<span data-ttu-id="f11c2-117">En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="f11c2-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="f11c2-118">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f11c2-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="f11c2-119">false</span><span class="sxs-lookup"><span data-stu-id="f11c2-119">false</span></span>|<span data-ttu-id="f11c2-120">Revierte al comportamiento de inicio de las versiones anteriores del .NET Framework, que era copiar todos los archivos en el inicio.</span><span class="sxs-lookup"><span data-stu-id="f11c2-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f11c2-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f11c2-121">Child Elements</span></span>  

 <span data-ttu-id="f11c2-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f11c2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f11c2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f11c2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f11c2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f11c2-124">Element</span></span>|<span data-ttu-id="f11c2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f11c2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f11c2-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11c2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f11c2-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f11c2-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f11c2-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f11c2-128">Remarks</span></span>  

 <span data-ttu-id="f11c2-129">A partir de la .NET Framework 4, los ensamblados solo se copian con instantáneas si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="f11c2-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="f11c2-130">Esto mejora los tiempos de inicio de muchas aplicaciones que usan la copia sombra, como se describe en [instantáneas de copia de ensamblados](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="f11c2-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="f11c2-131">Es posible que las aplicaciones que tienen un alto porcentaje y la frecuencia de las actualizaciones del ensamblado no se beneficien de este cambio de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f11c2-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="f11c2-132">En ese caso, puede usar este elemento para restaurar el comportamiento de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11c2-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11c2-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f11c2-133">Example</span></span>  

 <span data-ttu-id="f11c2-134">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminado de la copia sombra en el .NET Framework 4 y cómo revertir al comportamiento de inicio de versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11c2-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f11c2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f11c2-135">See also</span></span>

- [<span data-ttu-id="f11c2-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f11c2-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f11c2-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f11c2-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f11c2-138">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="f11c2-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
