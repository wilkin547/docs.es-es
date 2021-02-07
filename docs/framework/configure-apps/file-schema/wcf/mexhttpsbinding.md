---
description: 'Más información acerca de: <mexHttpsBinding>'
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 1e6eb66e1379cb8f351e34d4fd406dd3cc1f9a4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684339"
---
# \<mexHttpsBinding>

<span data-ttu-id="5ff07-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5ff07-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="5ff07-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ff07-103">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ff07-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ff07-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5ff07-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5ff07-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ff07-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ff07-106">Attributes</span></span>  
  
|<span data-ttu-id="5ff07-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ff07-107">Attribute</span></span>|<span data-ttu-id="5ff07-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ff07-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5ff07-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="5ff07-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5ff07-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ff07-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ff07-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ff07-111">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="5ff07-112">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="5ff07-112">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5ff07-113">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="5ff07-113">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5ff07-114">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="5ff07-114">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5ff07-115">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ff07-115">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5ff07-116">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="5ff07-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5ff07-117">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ff07-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ff07-118">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ff07-118">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5ff07-119">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="5ff07-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5ff07-120">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ff07-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ff07-121">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="5ff07-121">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5ff07-122">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="5ff07-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5ff07-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ff07-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ff07-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ff07-124">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ff07-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ff07-125">Child Elements</span></span>  

 <span data-ttu-id="5ff07-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5ff07-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ff07-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ff07-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5ff07-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ff07-128">Element</span></span>|<span data-ttu-id="5ff07-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ff07-129">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="5ff07-130">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="5ff07-130">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff07-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ff07-131">Remarks</span></span>  

 <span data-ttu-id="5ff07-132">Este enlace es esencialmente un enlace `WSHttpBinding` que admite seguridad de nivel de transporte mediante los certificados.</span><span class="sxs-lookup"><span data-stu-id="5ff07-132">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="5ff07-133">Para obtener más información sobre la configuración y el uso de este punto de conexión de metadatos, consulte [Cómo: configurar un enlace de intercambio personalizado WS-Metadata](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Cómo: recuperar metadatos a través de un enlace no Mex](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)y el [extremo de metadatos seguro personalizado](../../../wcf/samples/custom-secure-metadata-endpoint.md)de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5ff07-133">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff07-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff07-134">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="5ff07-135">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5ff07-135">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="5ff07-136">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="5ff07-136">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="5ff07-137">Procedimiento para configurar un enlace de WS-Metadata Exchange personalizado</span><span class="sxs-lookup"><span data-stu-id="5ff07-137">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="5ff07-138">Procedimiento para recuperar metadatos mediante un enlace que no sea MEX</span><span class="sxs-lookup"><span data-stu-id="5ff07-138">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="5ff07-139">Extremo personalizado de metadatos seguros</span><span class="sxs-lookup"><span data-stu-id="5ff07-139">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="5ff07-140">Metadata</span><span class="sxs-lookup"><span data-stu-id="5ff07-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="5ff07-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5ff07-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ff07-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5ff07-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5ff07-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5ff07-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
