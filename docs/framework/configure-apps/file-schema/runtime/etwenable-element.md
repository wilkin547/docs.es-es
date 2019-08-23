---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3510cbf0a63a8031669bb7a819a8b3c7321aaea4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920762"
---
# <a name="etwenable-element"></a><span data-ttu-id="2dfc4-102">\<etwEnable >, elemento</span><span class="sxs-lookup"><span data-stu-id="2dfc4-102">\<etwEnable> Element</span></span>
<span data-ttu-id="2dfc4-103">Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="2dfc4-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="2dfc4-104">\<configuration> Element</span></span>  
<span data-ttu-id="2dfc4-105">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2dfc4-105">\<runtime> Element</span></span>  
<span data-ttu-id="2dfc4-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="2dfc4-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dfc4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2dfc4-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dfc4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2dfc4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2dfc4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dfc4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2dfc4-110">Attributes</span></span>  
  
|<span data-ttu-id="2dfc4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2dfc4-111">Attribute</span></span>|<span data-ttu-id="2dfc4-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2dfc4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dfc4-113">enabled</span><span class="sxs-lookup"><span data-stu-id="2dfc4-113">enabled</span></span>|<span data-ttu-id="2dfc4-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2dfc4-115">Especifica si ETW debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2dfc4-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="2dfc4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2dfc4-117">Value</span><span class="sxs-lookup"><span data-stu-id="2dfc4-117">Value</span></span>|<span data-ttu-id="2dfc4-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2dfc4-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2dfc4-119">true</span><span class="sxs-lookup"><span data-stu-id="2dfc4-119">true</span></span>|<span data-ttu-id="2dfc4-120">Habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-120">Enable ETW.</span></span> <span data-ttu-id="2dfc4-121">Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="2dfc4-122">false</span><span class="sxs-lookup"><span data-stu-id="2dfc4-122">false</span></span>|<span data-ttu-id="2dfc4-123">Deshabilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-123">Disable ETW.</span></span> <span data-ttu-id="2dfc4-124">Este es el valor predeterminado para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dfc4-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2dfc4-125">Child Elements</span></span>  
 <span data-ttu-id="2dfc4-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dfc4-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2dfc4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2dfc4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="2dfc4-128">Element</span></span>|<span data-ttu-id="2dfc4-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2dfc4-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2dfc4-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2dfc4-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dfc4-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2dfc4-132">Remarks</span></span>  
 <span data-ttu-id="2dfc4-133">A partir de Windows Vista, ETW está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="2dfc4-134">Use este elemento para deshabilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="2dfc4-135">En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2dfc4-136">ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="2dfc4-137">Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="2dfc4-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dfc4-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2dfc4-138">Example</span></span>  
 <span data-ttu-id="2dfc4-139">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2dfc4-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dfc4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dfc4-140">See also</span></span>

- [<span data-ttu-id="2dfc4-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2dfc4-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2dfc4-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2dfc4-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2dfc4-143">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2dfc4-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
