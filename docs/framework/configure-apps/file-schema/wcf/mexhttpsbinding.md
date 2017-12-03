---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4990965e364765628174f9e8765663c7a7df70d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="5d221-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5d221-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="5d221-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5d221-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="5d221-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5d221-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d221-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5d221-105">\<bindings></span></span>  
<span data-ttu-id="5d221-106">\<mexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="5d221-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d221-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d221-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d221-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d221-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d221-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d221-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d221-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d221-110">Attributes</span></span>  
  
|<span data-ttu-id="5d221-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d221-111">Attribute</span></span>|<span data-ttu-id="5d221-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d221-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5d221-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="5d221-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5d221-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5d221-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d221-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5d221-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="5d221-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="5d221-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5d221-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="5d221-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5d221-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="5d221-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="5d221-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="5d221-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="5d221-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="5d221-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5d221-121">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d221-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5d221-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="5d221-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5d221-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5d221-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d221-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5d221-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5d221-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="5d221-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5d221-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5d221-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d221-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="5d221-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5d221-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="5d221-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5d221-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5d221-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d221-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5d221-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d221-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d221-131">Child Elements</span></span>  
 <span data-ttu-id="5d221-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d221-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d221-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d221-133">Parent Elements</span></span>  
  
|<span data-ttu-id="5d221-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d221-134">Element</span></span>|<span data-ttu-id="5d221-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d221-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d221-136">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5d221-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="5d221-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="5d221-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d221-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d221-138">Remarks</span></span>  
 <span data-ttu-id="5d221-139">Este enlace es esencialmente un enlace `WSHttpBinding` que admite seguridad de nivel de transporte mediante los certificados.</span><span class="sxs-lookup"><span data-stu-id="5d221-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="5d221-140">Para obtener más información acerca de cómo configurar y usar un punto de conexión de metadatos, vea [Cómo: configurar un enlace de personalizado WS-Metadata Exchange](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Cómo: recuperar metadatos sobre un no enlace MEX](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)y el ejemplo [extremo de metadatos seguros personalizado](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="5d221-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d221-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d221-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="5d221-142">Cómo: publicar los metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5d221-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="5d221-143">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="5d221-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="5d221-144">Cómo: configurar un personalizados WS-Metadata Exchange Binding</span><span class="sxs-lookup"><span data-stu-id="5d221-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="5d221-145">Cómo: recuperar metadatos mediante un no enlace MEX</span><span class="sxs-lookup"><span data-stu-id="5d221-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="5d221-146">Punto de conexión de metadatos seguro personalizado</span><span class="sxs-lookup"><span data-stu-id="5d221-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="5d221-147">Metadatos</span><span class="sxs-lookup"><span data-stu-id="5d221-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="5d221-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5d221-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5d221-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5d221-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5d221-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5d221-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5d221-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5d221-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
