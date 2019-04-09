---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 9ac2b967e33571cbe0b4ad5ee81e13b009ffddd3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111369"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="a6ae1-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="a6ae1-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="a6ae1-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="a6ae1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a6ae1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6ae1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a6ae1-104">\<bindings></span></span>  
<span data-ttu-id="a6ae1-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="a6ae1-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ae1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6ae1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ae1-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6ae1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a6ae1-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ae1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6ae1-109">Attributes</span></span>  
  
|<span data-ttu-id="a6ae1-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6ae1-110">Attribute</span></span>|<span data-ttu-id="a6ae1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ae1-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a6ae1-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a6ae1-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6ae1-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a6ae1-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a6ae1-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a6ae1-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="a6ae1-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="a6ae1-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a6ae1-120">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6ae1-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a6ae1-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a6ae1-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6ae1-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a6ae1-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a6ae1-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6ae1-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a6ae1-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a6ae1-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6ae1-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6ae1-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6ae1-130">Child Elements</span></span>  
 <span data-ttu-id="a6ae1-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ae1-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6ae1-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ae1-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ae1-133">Element</span></span>|<span data-ttu-id="a6ae1-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ae1-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ae1-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a6ae1-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="a6ae1-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="a6ae1-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6ae1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ae1-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="a6ae1-138">Filtrar para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a6ae1-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a6ae1-139">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="a6ae1-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a6ae1-140">Metadatos</span><span class="sxs-lookup"><span data-stu-id="a6ae1-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="a6ae1-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a6ae1-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a6ae1-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a6ae1-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a6ae1-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a6ae1-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a6ae1-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="a6ae1-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
