---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 4c3858ee0dc7fd20bd1269c74a4499998d530f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733992"
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="e46ff-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e46ff-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="e46ff-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="e46ff-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="e46ff-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e46ff-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e46ff-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e46ff-105">\<bindings></span></span>  
<span data-ttu-id="e46ff-106">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e46ff-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46ff-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e46ff-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e46ff-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e46ff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e46ff-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e46ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e46ff-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e46ff-110">Attributes</span></span>  
  
|<span data-ttu-id="e46ff-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e46ff-111">Attribute</span></span>|<span data-ttu-id="e46ff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e46ff-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e46ff-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="e46ff-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e46ff-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e46ff-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46ff-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e46ff-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="e46ff-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="e46ff-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e46ff-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="e46ff-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e46ff-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="e46ff-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="e46ff-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e46ff-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="e46ff-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="e46ff-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e46ff-121">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e46ff-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e46ff-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="e46ff-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e46ff-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e46ff-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46ff-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e46ff-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e46ff-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="e46ff-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e46ff-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e46ff-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46ff-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e46ff-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e46ff-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="e46ff-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e46ff-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e46ff-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46ff-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e46ff-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e46ff-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e46ff-131">Child Elements</span></span>  
 <span data-ttu-id="e46ff-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e46ff-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e46ff-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e46ff-133">Parent Elements</span></span>  
  
|<span data-ttu-id="e46ff-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="e46ff-134">Element</span></span>|<span data-ttu-id="e46ff-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="e46ff-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e46ff-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e46ff-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="e46ff-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="e46ff-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e46ff-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="e46ff-138">See also</span></span>
- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="e46ff-139">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e46ff-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="e46ff-140">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="e46ff-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="e46ff-141">Metadatos</span><span class="sxs-lookup"><span data-stu-id="e46ff-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="e46ff-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e46ff-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e46ff-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e46ff-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e46ff-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e46ff-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e46ff-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="e46ff-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
