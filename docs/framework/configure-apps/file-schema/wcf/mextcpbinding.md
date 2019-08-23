---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932531"
---
# <a name="mextcpbinding"></a><span data-ttu-id="5eb0b-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="5eb0b-101">\<mexTcpBinding></span></span>
<span data-ttu-id="5eb0b-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="5eb0b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5eb0b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5eb0b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5eb0b-104">\<bindings></span></span>  
<span data-ttu-id="5eb0b-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="5eb0b-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb0b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eb0b-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eb0b-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5eb0b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5eb0b-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eb0b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5eb0b-109">Attributes</span></span>  
  
|<span data-ttu-id="5eb0b-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="5eb0b-110">Attribute</span></span>|<span data-ttu-id="5eb0b-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5eb0b-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5eb0b-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5eb0b-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5eb0b-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="5eb0b-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5eb0b-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5eb0b-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="5eb0b-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="5eb0b-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5eb0b-120">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5eb0b-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5eb0b-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5eb0b-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5eb0b-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5eb0b-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5eb0b-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5eb0b-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5eb0b-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5eb0b-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5eb0b-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5eb0b-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5eb0b-130">Child Elements</span></span>  
 <span data-ttu-id="5eb0b-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5eb0b-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5eb0b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="5eb0b-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5eb0b-133">Element</span></span>|<span data-ttu-id="5eb0b-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5eb0b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5eb0b-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5eb0b-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="5eb0b-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5eb0b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eb0b-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="5eb0b-138">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5eb0b-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="5eb0b-139">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="5eb0b-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="5eb0b-140">Metadatos</span><span class="sxs-lookup"><span data-stu-id="5eb0b-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="5eb0b-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5eb0b-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5eb0b-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5eb0b-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5eb0b-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5eb0b-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5eb0b-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="5eb0b-144">\<binding></span></span>](../../../misc/binding.md)
