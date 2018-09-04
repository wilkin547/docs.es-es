---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8c2b149f983c0674b51c2242600a451ff71fc9b5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43540495"
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="8e1d3-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8e1d3-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="8e1d3-103">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="8e1d3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e1d3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e1d3-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8e1d3-105">\<bindings></span></span>  
<span data-ttu-id="8e1d3-106">\<mexTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="8e1d3-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e1d3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e1d3-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e1d3-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e1d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8e1d3-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e1d3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e1d3-110">Attributes</span></span>  
  
|<span data-ttu-id="8e1d3-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e1d3-111">Attribute</span></span>|<span data-ttu-id="8e1d3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e1d3-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8e1d3-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8e1d3-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8e1d3-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="8e1d3-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8e1d3-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8e1d3-118">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8e1d3-119">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8e1d3-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8e1d3-121">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d3-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8e1d3-122">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8e1d3-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8e1d3-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8e1d3-125">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8e1d3-126">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8e1d3-127">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8e1d3-128">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8e1d3-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8e1d3-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e1d3-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e1d3-131">Child Elements</span></span>  
 <span data-ttu-id="8e1d3-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e1d3-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e1d3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="8e1d3-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e1d3-134">Element</span></span>|<span data-ttu-id="8e1d3-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e1d3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e1d3-136">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8e1d3-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8e1d3-137">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="8e1d3-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e1d3-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e1d3-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>  
 [<span data-ttu-id="8e1d3-139">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8e1d3-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="8e1d3-140">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8e1d3-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="8e1d3-141">Metadatos</span><span class="sxs-lookup"><span data-stu-id="8e1d3-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="8e1d3-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8e1d3-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8e1d3-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8e1d3-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8e1d3-144">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8e1d3-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8e1d3-145">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8e1d3-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
