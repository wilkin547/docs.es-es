---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 0d12f886eaee6283ee686209dfc129e397a8e1fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204702"
---
# \<mexTcpBinding>

<span data-ttu-id="4eb5c-101">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="4eb5c-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4eb5c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4eb5c-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4eb5c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4eb5c-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4eb5c-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="4eb5c-105">Attributes</span></span>  
  
|<span data-ttu-id="4eb5c-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="4eb5c-106">Attribute</span></span>|<span data-ttu-id="4eb5c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4eb5c-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="4eb5c-108">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4eb5c-109">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4eb5c-110">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="4eb5c-111">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="4eb5c-112">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4eb5c-113">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4eb5c-114">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4eb5c-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="4eb5c-115">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4eb5c-116">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4eb5c-117">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4eb5c-118">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4eb5c-119">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4eb5c-120">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="4eb5c-121">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4eb5c-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4eb5c-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4eb5c-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4eb5c-124">Child Elements</span></span>  

 <span data-ttu-id="4eb5c-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4eb5c-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4eb5c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4eb5c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4eb5c-127">Element</span></span>|<span data-ttu-id="4eb5c-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="4eb5c-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="4eb5c-129">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="4eb5c-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4eb5c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4eb5c-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="4eb5c-131">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4eb5c-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="4eb5c-132">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="4eb5c-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="4eb5c-133">Metadata</span><span class="sxs-lookup"><span data-stu-id="4eb5c-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="4eb5c-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4eb5c-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4eb5c-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="4eb5c-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4eb5c-136">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4eb5c-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
