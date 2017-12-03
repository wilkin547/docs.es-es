---
title: '&lt;mexHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf21cf6615f7f36e7bbe9e352194bf3b76db6c12
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="f538c-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f538c-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="f538c-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="f538c-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="f538c-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f538c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f538c-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f538c-105">\<bindings></span></span>  
<span data-ttu-id="f538c-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f538c-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f538c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f538c-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f538c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f538c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f538c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f538c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f538c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f538c-110">Attributes</span></span>  
  
|<span data-ttu-id="f538c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f538c-111">Attribute</span></span>|<span data-ttu-id="f538c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f538c-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f538c-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="f538c-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f538c-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f538c-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f538c-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f538c-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="f538c-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="f538c-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f538c-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="f538c-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f538c-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="f538c-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="f538c-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f538c-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="f538c-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="f538c-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f538c-121">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f538c-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f538c-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="f538c-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f538c-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f538c-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f538c-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f538c-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f538c-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="f538c-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f538c-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f538c-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f538c-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="f538c-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f538c-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="f538c-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f538c-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f538c-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f538c-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f538c-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f538c-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f538c-131">Child Elements</span></span>  
 <span data-ttu-id="f538c-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f538c-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f538c-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f538c-133">Parent Elements</span></span>  
  
|<span data-ttu-id="f538c-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="f538c-134">Element</span></span>|<span data-ttu-id="f538c-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="f538c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f538c-136">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f538c-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="f538c-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="f538c-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f538c-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f538c-138">Remarks</span></span>  
 <span data-ttu-id="f538c-139">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f538c-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="f538c-140">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f538c-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f538c-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="f538c-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="f538c-142">Cómo: publicar los metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f538c-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="f538c-143">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f538c-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="f538c-144">Metadatos</span><span class="sxs-lookup"><span data-stu-id="f538c-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="f538c-145">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f538c-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f538c-146">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f538c-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f538c-147">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f538c-147">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f538c-148">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f538c-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
