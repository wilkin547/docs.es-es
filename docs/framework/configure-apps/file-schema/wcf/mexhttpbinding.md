---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 1aa9512c3d0d52f8cc3c7bd7b82bcfd37c418ce7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151247"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="d9905-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d9905-101">\<mexHttpBinding></span></span>
<span data-ttu-id="d9905-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="d9905-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="d9905-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9905-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9905-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d9905-104">\<bindings></span></span>  
<span data-ttu-id="d9905-105">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d9905-105">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9905-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9905-106">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9905-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9905-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d9905-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9905-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9905-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9905-109">Attributes</span></span>  
  
|<span data-ttu-id="d9905-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="d9905-110">Attribute</span></span>|<span data-ttu-id="d9905-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9905-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d9905-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="d9905-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d9905-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d9905-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9905-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9905-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d9905-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="d9905-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d9905-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d9905-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d9905-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="d9905-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d9905-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="d9905-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d9905-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="d9905-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d9905-120">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d9905-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d9905-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="d9905-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d9905-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d9905-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9905-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9905-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d9905-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="d9905-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d9905-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d9905-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9905-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d9905-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d9905-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="d9905-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d9905-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d9905-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9905-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9905-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9905-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9905-130">Child Elements</span></span>  
 <span data-ttu-id="d9905-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9905-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9905-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9905-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d9905-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9905-133">Element</span></span>|<span data-ttu-id="d9905-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9905-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9905-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d9905-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="d9905-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="d9905-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9905-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9905-137">Remarks</span></span>  
 <span data-ttu-id="d9905-138">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="d9905-138">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="d9905-139">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d9905-139">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9905-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9905-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="d9905-141">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d9905-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d9905-142">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="d9905-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d9905-143">Metadatos</span><span class="sxs-lookup"><span data-stu-id="d9905-143">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="d9905-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d9905-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d9905-145">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d9905-145">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d9905-146">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d9905-146">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d9905-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="d9905-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
