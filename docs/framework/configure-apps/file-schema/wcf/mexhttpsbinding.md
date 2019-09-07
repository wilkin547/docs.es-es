---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: d32db2180e06cba6662ed853ab1a259805680ea1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397823"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="588a0-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="588a0-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="588a0-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="588a0-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="588a0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="588a0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="588a0-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="588a0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="588a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="588a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="588a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> mexHttpsBinding**</span><span class="sxs-lookup"><span data-stu-id="588a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588a0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="588a0-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="588a0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="588a0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="588a0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="588a0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="588a0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="588a0-110">Attributes</span></span>  
  
|<span data-ttu-id="588a0-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="588a0-111">Attribute</span></span>|<span data-ttu-id="588a0-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="588a0-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="588a0-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="588a0-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="588a0-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="588a0-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="588a0-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="588a0-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="588a0-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="588a0-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="588a0-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="588a0-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="588a0-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="588a0-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="588a0-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="588a0-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="588a0-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="588a0-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="588a0-121">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="588a0-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="588a0-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="588a0-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="588a0-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="588a0-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="588a0-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="588a0-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="588a0-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="588a0-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="588a0-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="588a0-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="588a0-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="588a0-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="588a0-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="588a0-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="588a0-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="588a0-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="588a0-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="588a0-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="588a0-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="588a0-131">Child Elements</span></span>  
 <span data-ttu-id="588a0-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="588a0-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="588a0-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="588a0-133">Parent Elements</span></span>  
  
|<span data-ttu-id="588a0-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="588a0-134">Element</span></span>|<span data-ttu-id="588a0-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="588a0-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="588a0-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="588a0-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="588a0-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="588a0-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="588a0-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="588a0-138">Remarks</span></span>  
 <span data-ttu-id="588a0-139">Este enlace es esencialmente un enlace `WSHttpBinding` que admite seguridad de nivel de transporte mediante los certificados.</span><span class="sxs-lookup"><span data-stu-id="588a0-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="588a0-140">Para obtener más información sobre la configuración y el uso de este extremo [de metadatos, consulte Cómo: Configurar un enlace](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)de WS-Metadata Exchange personalizado [, cómo: Recupere los metadatos a través de](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)un enlace no Mex y el [extremo de metadatos seguro personalizado](../../../wcf/samples/custom-secure-metadata-endpoint.md)de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="588a0-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="588a0-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="588a0-141">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="588a0-142">Procedimientos: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="588a0-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="588a0-143">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="588a0-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="588a0-144">Procedimientos: Configuración de un enlace de WS-Metadata Exchange personalizado</span><span class="sxs-lookup"><span data-stu-id="588a0-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="588a0-145">Cómo: Recuperación de metadatos a través de un enlace no MEX</span><span class="sxs-lookup"><span data-stu-id="588a0-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="588a0-146">Punto de conexión personalizado de metadatos seguros</span><span class="sxs-lookup"><span data-stu-id="588a0-146">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="588a0-147">Metadatos</span><span class="sxs-lookup"><span data-stu-id="588a0-147">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="588a0-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="588a0-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="588a0-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="588a0-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="588a0-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="588a0-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="588a0-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="588a0-151">\<binding></span></span>](../../../misc/binding.md)
