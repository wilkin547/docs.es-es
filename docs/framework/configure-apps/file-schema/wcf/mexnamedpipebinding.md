---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430877"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="6ed31-101">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="6ed31-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="6ed31-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="6ed31-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="6ed31-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ed31-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6ed31-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6ed31-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6ed31-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="6ed31-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6ed31-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexNamedPipeBinding >**</span><span class="sxs-lookup"><span data-stu-id="6ed31-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed31-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ed31-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ed31-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ed31-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6ed31-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ed31-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ed31-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ed31-110">Attributes</span></span>  
  
|<span data-ttu-id="6ed31-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ed31-111">Attribute</span></span>|<span data-ttu-id="6ed31-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ed31-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="6ed31-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="6ed31-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="6ed31-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="6ed31-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6ed31-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6ed31-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="6ed31-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="6ed31-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="6ed31-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="6ed31-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="6ed31-118">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="6ed31-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="6ed31-119">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="6ed31-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="6ed31-120">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="6ed31-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="6ed31-121">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="6ed31-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6ed31-122">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6ed31-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="6ed31-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="6ed31-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="6ed31-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="6ed31-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6ed31-125">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="6ed31-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="6ed31-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="6ed31-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="6ed31-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="6ed31-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6ed31-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6ed31-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ed31-129">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="6ed31-129">Child Elements</span></span>  
 <span data-ttu-id="6ed31-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ed31-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ed31-131">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="6ed31-131">Parent Elements</span></span>  
  
|<span data-ttu-id="6ed31-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ed31-132">Element</span></span>|<span data-ttu-id="6ed31-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ed31-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ed31-134">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="6ed31-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="6ed31-135">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="6ed31-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ed31-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ed31-136">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="6ed31-137">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="6ed31-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="6ed31-138">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="6ed31-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="6ed31-139">Metadatos</span><span class="sxs-lookup"><span data-stu-id="6ed31-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="6ed31-140">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6ed31-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6ed31-141">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6ed31-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6ed31-142">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6ed31-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6ed31-143">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="6ed31-143">\<binding></span></span>](bindings.md)
