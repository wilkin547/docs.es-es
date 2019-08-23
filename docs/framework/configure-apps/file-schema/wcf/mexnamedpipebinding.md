---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 0d0904c02e31def1b5264bec9f61eac0c9a8e964
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931231"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="7de1c-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="7de1c-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="7de1c-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="7de1c-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="7de1c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7de1c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7de1c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7de1c-104">\<bindings></span></span>  
<span data-ttu-id="7de1c-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="7de1c-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de1c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7de1c-106">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7de1c-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7de1c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7de1c-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7de1c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7de1c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7de1c-109">Attributes</span></span>  
  
|<span data-ttu-id="7de1c-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="7de1c-110">Attribute</span></span>|<span data-ttu-id="7de1c-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7de1c-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7de1c-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="7de1c-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7de1c-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7de1c-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7de1c-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7de1c-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="7de1c-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="7de1c-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7de1c-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="7de1c-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7de1c-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="7de1c-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="7de1c-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="7de1c-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="7de1c-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="7de1c-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7de1c-120">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7de1c-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7de1c-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="7de1c-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7de1c-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7de1c-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7de1c-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7de1c-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7de1c-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="7de1c-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7de1c-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7de1c-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7de1c-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7de1c-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7de1c-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="7de1c-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7de1c-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7de1c-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7de1c-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7de1c-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7de1c-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7de1c-130">Child Elements</span></span>  
 <span data-ttu-id="7de1c-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7de1c-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7de1c-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7de1c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="7de1c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="7de1c-133">Element</span></span>|<span data-ttu-id="7de1c-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7de1c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7de1c-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7de1c-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="7de1c-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="7de1c-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7de1c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7de1c-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="7de1c-138">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7de1c-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="7de1c-139">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="7de1c-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="7de1c-140">Metadatos</span><span class="sxs-lookup"><span data-stu-id="7de1c-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="7de1c-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7de1c-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7de1c-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7de1c-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7de1c-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7de1c-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7de1c-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="7de1c-144">\<binding></span></span>](../../../misc/binding.md)
