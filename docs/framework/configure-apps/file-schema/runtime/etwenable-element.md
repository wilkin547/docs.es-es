---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 1c3e42dfbc2c27841ed065e90bad24575e4fb2b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178273"
---
# <a name="etwenable-element"></a><span data-ttu-id="82618-102">\<etwEnable> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="82618-102">\<etwEnable> Element</span></span>

<span data-ttu-id="82618-103">Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="82618-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="82618-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82618-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82618-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82618-105">Attributes and Elements</span></span>  

 <span data-ttu-id="82618-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82618-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82618-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="82618-107">Attributes</span></span>  
  
|<span data-ttu-id="82618-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="82618-108">Attribute</span></span>|<span data-ttu-id="82618-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="82618-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82618-110">enabled</span><span class="sxs-lookup"><span data-stu-id="82618-110">enabled</span></span>|<span data-ttu-id="82618-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="82618-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="82618-112">Especifica si ETW debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="82618-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="82618-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="82618-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="82618-114">Value</span><span class="sxs-lookup"><span data-stu-id="82618-114">Value</span></span>|<span data-ttu-id="82618-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="82618-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82618-116">true</span><span class="sxs-lookup"><span data-stu-id="82618-116">true</span></span>|<span data-ttu-id="82618-117">Habilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="82618-117">Enable ETW.</span></span> <span data-ttu-id="82618-118">Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="82618-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="82618-119">false</span><span class="sxs-lookup"><span data-stu-id="82618-119">false</span></span>|<span data-ttu-id="82618-120">Deshabilitar ETW.</span><span class="sxs-lookup"><span data-stu-id="82618-120">Disable ETW.</span></span> <span data-ttu-id="82618-121">Este es el valor predeterminado para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="82618-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82618-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82618-122">Child Elements</span></span>  

 <span data-ttu-id="82618-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="82618-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82618-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82618-124">Parent Elements</span></span>  
  
|<span data-ttu-id="82618-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="82618-125">Element</span></span>|<span data-ttu-id="82618-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="82618-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="82618-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82618-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="82618-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="82618-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82618-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82618-129">Remarks</span></span>  

 <span data-ttu-id="82618-130">A partir de Windows Vista, ETW está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82618-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="82618-131">Use este elemento para deshabilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="82618-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="82618-132">En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="82618-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82618-133">ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="82618-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="82618-134">Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="82618-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82618-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82618-135">Example</span></span>  

 <span data-ttu-id="82618-136">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de ETW para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="82618-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="82618-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82618-137">See also</span></span>

- [<span data-ttu-id="82618-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="82618-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="82618-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="82618-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="82618-140">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="82618-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
