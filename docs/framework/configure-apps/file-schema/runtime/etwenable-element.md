---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117392"
---
# <a name="etwenable-element"></a><span data-ttu-id="bb9c5-102">\<etwEnable> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="bb9c5-102">\<etwEnable> Element</span></span>
<span data-ttu-id="bb9c5-103">Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="bb9c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb9c5-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb9c5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bb9c5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bb9c5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb9c5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb9c5-107">Attributes</span></span>  
  
|<span data-ttu-id="bb9c5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="bb9c5-108">Attribute</span></span>|<span data-ttu-id="bb9c5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb9c5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb9c5-110">enabled</span><span class="sxs-lookup"><span data-stu-id="bb9c5-110">enabled</span></span>|<span data-ttu-id="bb9c5-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb9c5-112">Especifica si ETW debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb9c5-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="bb9c5-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb9c5-114">Value</span><span class="sxs-lookup"><span data-stu-id="bb9c5-114">Value</span></span>|<span data-ttu-id="bb9c5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb9c5-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb9c5-116">true</span><span class="sxs-lookup"><span data-stu-id="bb9c5-116">true</span></span>|<span data-ttu-id="bb9c5-117">Habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-117">Enable ETW.</span></span> <span data-ttu-id="bb9c5-118">Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="bb9c5-119">false</span><span class="sxs-lookup"><span data-stu-id="bb9c5-119">false</span></span>|<span data-ttu-id="bb9c5-120">Deshabilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-120">Disable ETW.</span></span> <span data-ttu-id="bb9c5-121">Este es el valor predeterminado para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb9c5-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bb9c5-122">Child Elements</span></span>  
 <span data-ttu-id="bb9c5-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb9c5-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bb9c5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bb9c5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb9c5-125">Element</span></span>|<span data-ttu-id="bb9c5-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb9c5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb9c5-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb9c5-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb9c5-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb9c5-129">Remarks</span></span>  
 <span data-ttu-id="bb9c5-130">A partir de Windows Vista, ETW está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="bb9c5-131">Use este elemento para deshabilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="bb9c5-132">En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb9c5-133">ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="bb9c5-134">Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="bb9c5-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb9c5-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb9c5-135">Example</span></span>  
 <span data-ttu-id="bb9c5-136">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb9c5-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb9c5-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb9c5-137">See also</span></span>

- [<span data-ttu-id="bb9c5-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bb9c5-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb9c5-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bb9c5-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb9c5-140">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb9c5-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
