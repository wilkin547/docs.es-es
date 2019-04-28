---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704809"
---
# <a name="etwenable-element"></a><span data-ttu-id="f8d9b-102">\<etwEnable > elemento</span><span class="sxs-lookup"><span data-stu-id="f8d9b-102">\<etwEnable> Element</span></span>
<span data-ttu-id="f8d9b-103">Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="f8d9b-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="f8d9b-104">\<configuration> Element</span></span>  
<span data-ttu-id="f8d9b-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="f8d9b-105">\<runtime> Element</span></span>  
<span data-ttu-id="f8d9b-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="f8d9b-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d9b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8d9b-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8d9b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f8d9b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f8d9b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8d9b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f8d9b-110">Attributes</span></span>  
  
|<span data-ttu-id="f8d9b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f8d9b-111">Attribute</span></span>|<span data-ttu-id="f8d9b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8d9b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8d9b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="f8d9b-113">enabled</span></span>|<span data-ttu-id="f8d9b-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f8d9b-115">Especifica si se debe habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f8d9b-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="f8d9b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="f8d9b-117">Valor</span><span class="sxs-lookup"><span data-stu-id="f8d9b-117">Value</span></span>|<span data-ttu-id="f8d9b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8d9b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8d9b-119">true</span><span class="sxs-lookup"><span data-stu-id="f8d9b-119">true</span></span>|<span data-ttu-id="f8d9b-120">Habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-120">Enable ETW.</span></span> <span data-ttu-id="f8d9b-121">Este es el valor predeterminado para las versiones de Windows empezando con los sistemas operativos Windows Vista y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="f8d9b-122">False</span><span class="sxs-lookup"><span data-stu-id="f8d9b-122">false</span></span>|<span data-ttu-id="f8d9b-123">Deshabilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-123">Disable ETW.</span></span> <span data-ttu-id="f8d9b-124">Este es el valor predeterminado para las versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8d9b-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f8d9b-125">Child Elements</span></span>  
 <span data-ttu-id="f8d9b-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8d9b-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f8d9b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f8d9b-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8d9b-128">Element</span></span>|<span data-ttu-id="f8d9b-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8d9b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f8d9b-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f8d9b-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8d9b-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8d9b-132">Remarks</span></span>  
 <span data-ttu-id="f8d9b-133">Comenzando con Windows Vista, ETW está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="f8d9b-134">Utilice este elemento para deshabilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="f8d9b-135">En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8d9b-136">Puede ser habilitado o deshabilitado globalmente en un servidor mediante una configuración del registro ETW.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="f8d9b-137">Consulte [controlar el registro de .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f8d9b-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d9b-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8d9b-138">Example</span></span>  
 <span data-ttu-id="f8d9b-139">El ejemplo siguiente muestra cómo habilitar el seguimiento de ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8d9b-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8d9b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8d9b-140">See also</span></span>

- [<span data-ttu-id="f8d9b-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f8d9b-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f8d9b-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f8d9b-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f8d9b-143">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f8d9b-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
