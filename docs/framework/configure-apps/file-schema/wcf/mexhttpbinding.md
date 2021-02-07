---
description: 'Más información acerca de: <mexHttpBinding>'
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: b95c73ed0576f769f046547152aff030efd49071
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684352"
---
# \<mexHttpBinding>

<span data-ttu-id="1257c-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="1257c-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="1257c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1257c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1257c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1257c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1257c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1257c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1257c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="1257c-106">Attributes</span></span>  
  
|<span data-ttu-id="1257c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="1257c-107">Attribute</span></span>|<span data-ttu-id="1257c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1257c-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="1257c-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="1257c-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1257c-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1257c-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1257c-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1257c-111">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="1257c-112">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="1257c-112">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1257c-113">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="1257c-113">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="1257c-114">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="1257c-114">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1257c-115">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1257c-115">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="1257c-116">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="1257c-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1257c-117">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1257c-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1257c-118">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1257c-118">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="1257c-119">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="1257c-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1257c-120">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1257c-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1257c-121">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="1257c-121">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="1257c-122">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="1257c-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1257c-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1257c-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1257c-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1257c-124">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1257c-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1257c-125">Child Elements</span></span>  

 <span data-ttu-id="1257c-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1257c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1257c-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1257c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1257c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1257c-128">Element</span></span>|<span data-ttu-id="1257c-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="1257c-129">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="1257c-130">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="1257c-130">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1257c-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1257c-131">Remarks</span></span>  

 <span data-ttu-id="1257c-132">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1257c-132">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="1257c-133">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="1257c-133">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1257c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1257c-134">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="1257c-135">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1257c-135">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="1257c-136">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="1257c-136">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="1257c-137">Metadata</span><span class="sxs-lookup"><span data-stu-id="1257c-137">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="1257c-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1257c-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1257c-139">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="1257c-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1257c-140">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1257c-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
