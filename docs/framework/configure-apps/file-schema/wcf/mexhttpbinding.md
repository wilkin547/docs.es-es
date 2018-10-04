---
title: '&lt;mexHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: a39bf98e803d8348dd70497d084775d1dd31d149
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793479"
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="ba46d-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ba46d-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="ba46d-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba46d-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="ba46d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba46d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba46d-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="ba46d-105">\<bindings></span></span>  
<span data-ttu-id="ba46d-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ba46d-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba46d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba46d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba46d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba46d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ba46d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba46d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba46d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba46d-110">Attributes</span></span>  
  
|<span data-ttu-id="ba46d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba46d-111">Attribute</span></span>|<span data-ttu-id="ba46d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba46d-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ba46d-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba46d-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ba46d-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba46d-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba46d-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba46d-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="ba46d-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="ba46d-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ba46d-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="ba46d-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ba46d-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="ba46d-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="ba46d-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="ba46d-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="ba46d-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="ba46d-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ba46d-121">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba46d-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ba46d-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba46d-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ba46d-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba46d-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba46d-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba46d-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ba46d-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba46d-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ba46d-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba46d-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba46d-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ba46d-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ba46d-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba46d-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ba46d-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba46d-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba46d-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba46d-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba46d-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba46d-131">Child Elements</span></span>  
 <span data-ttu-id="ba46d-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ba46d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba46d-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba46d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ba46d-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba46d-134">Element</span></span>|<span data-ttu-id="ba46d-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba46d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba46d-136">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="ba46d-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="ba46d-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="ba46d-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba46d-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba46d-138">Remarks</span></span>  
 <span data-ttu-id="ba46d-139">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="ba46d-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="ba46d-140">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ba46d-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba46d-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba46d-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="ba46d-142">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ba46d-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="ba46d-143">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="ba46d-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="ba46d-144">Metadatos</span><span class="sxs-lookup"><span data-stu-id="ba46d-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="ba46d-145">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ba46d-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ba46d-146">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ba46d-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ba46d-147">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ba46d-147">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="ba46d-148">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="ba46d-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
