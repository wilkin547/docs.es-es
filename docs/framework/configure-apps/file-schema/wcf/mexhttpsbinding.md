---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430336"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="99f17-101">\<mexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="99f17-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="99f17-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99f17-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="99f17-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99f17-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99f17-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99f17-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99f17-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="99f17-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="99f17-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpsBinding >**</span><span class="sxs-lookup"><span data-stu-id="99f17-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f17-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99f17-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99f17-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99f17-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99f17-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99f17-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99f17-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="99f17-110">Attributes</span></span>  
  
|<span data-ttu-id="99f17-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="99f17-111">Attribute</span></span>|<span data-ttu-id="99f17-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f17-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="99f17-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="99f17-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="99f17-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99f17-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99f17-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99f17-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="99f17-116">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="99f17-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="99f17-117">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="99f17-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="99f17-118">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="99f17-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="99f17-119">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="99f17-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="99f17-120">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="99f17-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="99f17-121">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99f17-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99f17-122">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99f17-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="99f17-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="99f17-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="99f17-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99f17-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99f17-125">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="99f17-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="99f17-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="99f17-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="99f17-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99f17-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99f17-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99f17-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99f17-129">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="99f17-129">Child Elements</span></span>  
 <span data-ttu-id="99f17-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99f17-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99f17-131">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="99f17-131">Parent Elements</span></span>  
  
|<span data-ttu-id="99f17-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="99f17-132">Element</span></span>|<span data-ttu-id="99f17-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f17-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99f17-134">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="99f17-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="99f17-135">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="99f17-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99f17-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99f17-136">Remarks</span></span>  
 <span data-ttu-id="99f17-137">Este enlace es esencialmente un enlace `WSHttpBinding` que admite seguridad de nivel de transporte mediante los certificados.</span><span class="sxs-lookup"><span data-stu-id="99f17-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="99f17-138">Para obtener más información sobre la configuración y el uso de este extremo de metadatos, consulte [Cómo: configurar un enlace de WS-Metadata Exchange personalizado](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Cómo: recuperar metadatos a través de un enlace no Mex](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)y el [extremo de metadatos seguro personalizado](../../../wcf/samples/custom-secure-metadata-endpoint.md)de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="99f17-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f17-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f17-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="99f17-140">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="99f17-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="99f17-141">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="99f17-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="99f17-142">Configuración de un enlace de WS-Metadata Exchange personalizado</span><span class="sxs-lookup"><span data-stu-id="99f17-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="99f17-143">Recuperación de metadatos mediante un enlace que no sea MEX</span><span class="sxs-lookup"><span data-stu-id="99f17-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="99f17-144">Punto de conexión personalizado de metadatos seguros</span><span class="sxs-lookup"><span data-stu-id="99f17-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="99f17-145">Metadatos</span><span class="sxs-lookup"><span data-stu-id="99f17-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="99f17-146">Enlaces</span><span class="sxs-lookup"><span data-stu-id="99f17-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99f17-147">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="99f17-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99f17-148">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="99f17-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="99f17-149">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="99f17-149">\<binding></span></span>](bindings.md)
