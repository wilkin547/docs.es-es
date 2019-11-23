---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430305"
---
# <a name="mextcpbinding"></a><span data-ttu-id="27957-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="27957-101">\<mexTcpBinding></span></span>
<span data-ttu-id="27957-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="27957-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="27957-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27957-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27957-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27957-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27957-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="27957-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="27957-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexTcpBinding>**</span><span class="sxs-lookup"><span data-stu-id="27957-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27957-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27957-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27957-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="27957-108">Attributes and Elements</span></span>  
 <span data-ttu-id="27957-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="27957-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27957-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="27957-110">Attributes</span></span>  
  
|<span data-ttu-id="27957-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="27957-111">Attribute</span></span>|<span data-ttu-id="27957-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="27957-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="27957-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="27957-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="27957-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="27957-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="27957-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="27957-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="27957-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="27957-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="27957-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="27957-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="27957-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="27957-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="27957-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="27957-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="27957-120">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="27957-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="27957-121">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="27957-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="27957-122">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="27957-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="27957-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="27957-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="27957-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="27957-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="27957-125">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="27957-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="27957-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="27957-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="27957-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="27957-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="27957-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="27957-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27957-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="27957-129">Child Elements</span></span>  
 <span data-ttu-id="27957-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="27957-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27957-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="27957-131">Parent Elements</span></span>  
  
|<span data-ttu-id="27957-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="27957-132">Element</span></span>|<span data-ttu-id="27957-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="27957-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27957-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="27957-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="27957-135">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="27957-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27957-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="27957-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="27957-137">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="27957-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="27957-138">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="27957-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="27957-139">Metadatos</span><span class="sxs-lookup"><span data-stu-id="27957-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="27957-140">Enlaces</span><span class="sxs-lookup"><span data-stu-id="27957-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="27957-141">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="27957-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="27957-142">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="27957-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="27957-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="27957-143">\<binding></span></span>](bindings.md)
