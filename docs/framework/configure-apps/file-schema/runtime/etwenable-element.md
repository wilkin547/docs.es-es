---
description: 'Más información acerca de: <etwEnable> elemento'
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 224784f47d15788ded41a5756e1d179a5a25907b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787050"
---
# <a name="etwenable-element"></a><span data-ttu-id="a4fef-103">\<etwEnable> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a4fef-103">\<etwEnable> Element</span></span>

<span data-ttu-id="a4fef-104">Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a4fef-104">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="a4fef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4fef-105">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4fef-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a4fef-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a4fef-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a4fef-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4fef-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4fef-108">Attributes</span></span>  
  
|<span data-ttu-id="a4fef-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a4fef-109">Attribute</span></span>|<span data-ttu-id="a4fef-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4fef-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4fef-111">enabled</span><span class="sxs-lookup"><span data-stu-id="a4fef-111">enabled</span></span>|<span data-ttu-id="a4fef-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a4fef-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4fef-113">Especifica si ETW debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="a4fef-113">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a4fef-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a4fef-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="a4fef-115">Value</span><span class="sxs-lookup"><span data-stu-id="a4fef-115">Value</span></span>|<span data-ttu-id="a4fef-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4fef-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4fef-117">true</span><span class="sxs-lookup"><span data-stu-id="a4fef-117">true</span></span>|<span data-ttu-id="a4fef-118">Habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="a4fef-118">Enable ETW.</span></span> <span data-ttu-id="a4fef-119">Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a4fef-119">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="a4fef-120">false</span><span class="sxs-lookup"><span data-stu-id="a4fef-120">false</span></span>|<span data-ttu-id="a4fef-121">Deshabilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="a4fef-121">Disable ETW.</span></span> <span data-ttu-id="a4fef-122">Este es el valor predeterminado para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="a4fef-122">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4fef-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a4fef-123">Child Elements</span></span>  

 <span data-ttu-id="a4fef-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a4fef-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4fef-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4fef-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a4fef-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4fef-126">Element</span></span>|<span data-ttu-id="a4fef-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4fef-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a4fef-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4fef-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a4fef-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a4fef-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4fef-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a4fef-130">Remarks</span></span>  

 <span data-ttu-id="a4fef-131">A partir de Windows Vista, ETW está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a4fef-131">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="a4fef-132">Use este elemento para deshabilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4fef-132">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="a4fef-133">En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4fef-133">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4fef-134">ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a4fef-134">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="a4fef-135">Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a4fef-135">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4fef-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4fef-136">Example</span></span>  

 <span data-ttu-id="a4fef-137">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4fef-137">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4fef-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4fef-138">See also</span></span>

- [<span data-ttu-id="a4fef-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a4fef-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a4fef-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a4fef-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a4fef-141">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a4fef-141">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
