---
description: 'Más información acerca de: <mexNamedPipeBinding>'
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: a7d1c6b10ed436d5ec1b20092d042d6b0a80bd34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684326"
---
# \<mexNamedPipeBinding>

<span data-ttu-id="94684-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="94684-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="94684-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94684-103">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94684-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="94684-104">Attributes and Elements</span></span>  

 <span data-ttu-id="94684-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="94684-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94684-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="94684-106">Attributes</span></span>  
  
|<span data-ttu-id="94684-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="94684-107">Attribute</span></span>|<span data-ttu-id="94684-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="94684-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="94684-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="94684-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="94684-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="94684-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="94684-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="94684-111">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="94684-112">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="94684-112">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="94684-113">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="94684-113">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="94684-114">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="94684-114">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="94684-115">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="94684-115">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="94684-116">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="94684-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="94684-117">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="94684-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="94684-118">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="94684-118">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="94684-119">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="94684-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="94684-120">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="94684-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="94684-121">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="94684-121">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="94684-122">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="94684-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="94684-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="94684-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="94684-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="94684-124">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94684-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="94684-125">Child Elements</span></span>  

 <span data-ttu-id="94684-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="94684-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94684-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="94684-127">Parent Elements</span></span>  
  
|<span data-ttu-id="94684-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="94684-128">Element</span></span>|<span data-ttu-id="94684-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="94684-129">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="94684-130">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="94684-130">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94684-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="94684-131">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="94684-132">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="94684-132">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="94684-133">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="94684-133">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="94684-134">Metadata</span><span class="sxs-lookup"><span data-stu-id="94684-134">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="94684-135">Enlaces</span><span class="sxs-lookup"><span data-stu-id="94684-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="94684-136">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="94684-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="94684-137">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="94684-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
