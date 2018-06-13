---
title: '&lt;mexHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 5822064af711c1a2c16bddfd142f415541b9604d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748817"
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="e4230-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e4230-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="e4230-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4230-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="e4230-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e4230-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e4230-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e4230-105">\<bindings></span></span>  
<span data-ttu-id="e4230-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e4230-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4230-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4230-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4230-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4230-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e4230-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4230-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4230-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4230-110">Attributes</span></span>  
  
|<span data-ttu-id="e4230-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4230-111">Attribute</span></span>|<span data-ttu-id="e4230-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4230-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e4230-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="e4230-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e4230-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e4230-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e4230-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e4230-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="e4230-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="e4230-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e4230-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="e4230-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e4230-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="e4230-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="e4230-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e4230-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="e4230-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="e4230-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e4230-121">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e4230-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e4230-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="e4230-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e4230-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e4230-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e4230-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e4230-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e4230-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="e4230-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e4230-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e4230-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e4230-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e4230-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e4230-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="e4230-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e4230-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e4230-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e4230-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e4230-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4230-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4230-131">Child Elements</span></span>  
 <span data-ttu-id="e4230-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e4230-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4230-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4230-133">Parent Elements</span></span>  
  
|<span data-ttu-id="e4230-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4230-134">Element</span></span>|<span data-ttu-id="e4230-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4230-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4230-136">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e4230-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="e4230-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="e4230-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4230-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4230-138">Remarks</span></span>  
 <span data-ttu-id="e4230-139">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e4230-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="e4230-140">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e4230-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4230-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4230-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="e4230-142">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e4230-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="e4230-143">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="e4230-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="e4230-144">Metadatos</span><span class="sxs-lookup"><span data-stu-id="e4230-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="e4230-145">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e4230-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e4230-146">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e4230-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e4230-147">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e4230-147">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e4230-148">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e4230-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
