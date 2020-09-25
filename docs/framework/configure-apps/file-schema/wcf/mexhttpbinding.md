---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8c15b06e60e4de6ede4c9a683a6701140533534c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204741"
---
# \<mexHttpBinding>

<span data-ttu-id="312e6-101">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="312e6-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="312e6-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="312e6-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="312e6-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="312e6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="312e6-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="312e6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="312e6-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="312e6-105">Attributes</span></span>  
  
|<span data-ttu-id="312e6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="312e6-106">Attribute</span></span>|<span data-ttu-id="312e6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="312e6-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="312e6-108">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="312e6-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="312e6-109">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="312e6-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="312e6-110">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="312e6-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="312e6-111">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="312e6-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="312e6-112">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="312e6-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="312e6-113">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="312e6-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="312e6-114">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="312e6-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="312e6-115">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="312e6-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="312e6-116">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="312e6-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="312e6-117">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="312e6-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="312e6-118">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="312e6-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="312e6-119">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="312e6-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="312e6-120">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="312e6-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="312e6-121">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="312e6-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="312e6-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="312e6-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="312e6-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="312e6-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="312e6-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="312e6-124">Child Elements</span></span>  

 <span data-ttu-id="312e6-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="312e6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="312e6-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="312e6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="312e6-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="312e6-127">Element</span></span>|<span data-ttu-id="312e6-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="312e6-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="312e6-129">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="312e6-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="312e6-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="312e6-130">Remarks</span></span>  

 <span data-ttu-id="312e6-131">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="312e6-131">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="312e6-132">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="312e6-132">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312e6-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="312e6-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="312e6-134">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="312e6-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="312e6-135">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="312e6-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="312e6-136">Metadata</span><span class="sxs-lookup"><span data-stu-id="312e6-136">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="312e6-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="312e6-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="312e6-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="312e6-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="312e6-139">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="312e6-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
