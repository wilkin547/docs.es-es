---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8d5b9378bf7769754586d0b13f742659aee18f03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430907"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="87f14-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="87f14-101">\<mexHttpBinding></span></span>
<span data-ttu-id="87f14-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="87f14-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="87f14-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87f14-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87f14-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="87f14-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="87f14-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="87f14-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="87f14-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding>**</span><span class="sxs-lookup"><span data-stu-id="87f14-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f14-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87f14-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87f14-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="87f14-108">Attributes and Elements</span></span>  
 <span data-ttu-id="87f14-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="87f14-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87f14-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="87f14-110">Attributes</span></span>  
  
|<span data-ttu-id="87f14-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="87f14-111">Attribute</span></span>|<span data-ttu-id="87f14-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="87f14-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="87f14-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="87f14-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="87f14-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="87f14-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="87f14-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="87f14-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="87f14-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="87f14-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="87f14-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="87f14-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="87f14-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="87f14-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="87f14-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="87f14-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="87f14-120">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="87f14-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="87f14-121">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="87f14-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="87f14-122">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="87f14-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="87f14-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="87f14-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="87f14-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="87f14-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="87f14-125">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="87f14-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="87f14-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="87f14-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="87f14-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="87f14-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="87f14-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="87f14-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87f14-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="87f14-129">Child Elements</span></span>  
 <span data-ttu-id="87f14-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="87f14-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87f14-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87f14-131">Parent Elements</span></span>  
  
|<span data-ttu-id="87f14-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="87f14-132">Element</span></span>|<span data-ttu-id="87f14-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="87f14-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87f14-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="87f14-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="87f14-135">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="87f14-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f14-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87f14-136">Remarks</span></span>  
 <span data-ttu-id="87f14-137">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="87f14-137">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="87f14-138">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="87f14-138">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f14-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="87f14-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="87f14-140">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="87f14-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="87f14-141">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="87f14-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="87f14-142">Metadatos</span><span class="sxs-lookup"><span data-stu-id="87f14-142">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="87f14-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="87f14-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="87f14-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="87f14-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="87f14-145">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="87f14-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="87f14-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="87f14-146">\<binding></span></span>](bindings.md)
