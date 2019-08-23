---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 30d1aa27ce29b6aa4091c3e7be05746ad462102a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931264"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="ab0a9-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="ab0a9-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="ab0a9-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="ab0a9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ab0a9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ab0a9-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ab0a9-104">\<bindings></span></span>  
<span data-ttu-id="ab0a9-105">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="ab0a9-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab0a9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab0a9-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab0a9-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ab0a9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ab0a9-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab0a9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab0a9-109">Attributes</span></span>  
  
|<span data-ttu-id="ab0a9-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ab0a9-110">Attribute</span></span>|<span data-ttu-id="ab0a9-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ab0a9-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ab0a9-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ab0a9-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab0a9-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="ab0a9-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ab0a9-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ab0a9-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="ab0a9-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="ab0a9-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ab0a9-120">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab0a9-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ab0a9-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ab0a9-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab0a9-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ab0a9-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ab0a9-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab0a9-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ab0a9-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ab0a9-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab0a9-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab0a9-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ab0a9-130">Child Elements</span></span>  
 <span data-ttu-id="ab0a9-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab0a9-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ab0a9-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ab0a9-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab0a9-133">Element</span></span>|<span data-ttu-id="ab0a9-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ab0a9-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab0a9-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ab0a9-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="ab0a9-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab0a9-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab0a9-137">Remarks</span></span>  
 <span data-ttu-id="ab0a9-138">Este enlace es esencialmente un enlace `WSHttpBinding` que admite seguridad de nivel de transporte mediante los certificados.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="ab0a9-139">Para obtener más información sobre la configuración y el uso de este extremo [de metadatos, consulte Cómo: Configurar un enlace](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)de WS-Metadata Exchange personalizado [, cómo: Recupere los metadatos a través de](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)un enlace no Mex y el extremo de metadatos [seguro personalizado](../../../wcf/samples/custom-secure-metadata-endpoint.md)de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ab0a9-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab0a9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab0a9-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="ab0a9-141">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ab0a9-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="ab0a9-142">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="ab0a9-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="ab0a9-143">Procedimientos: Configuración de un enlace personalizado de intercambio de WS-Metadata</span><span class="sxs-lookup"><span data-stu-id="ab0a9-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="ab0a9-144">Cómo: Recuperación de metadatos a través de un enlace no MEX</span><span class="sxs-lookup"><span data-stu-id="ab0a9-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="ab0a9-145">Punto de conexión personalizado de metadatos seguros</span><span class="sxs-lookup"><span data-stu-id="ab0a9-145">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="ab0a9-146">Metadatos</span><span class="sxs-lookup"><span data-stu-id="ab0a9-146">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="ab0a9-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ab0a9-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ab0a9-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ab0a9-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ab0a9-149">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ab0a9-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ab0a9-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="ab0a9-150">\<binding></span></span>](../../../misc/binding.md)
