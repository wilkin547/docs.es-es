---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 6cc8b80edb3206bb2ef3a8a1ffa34ab40af77612
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398152"
---
# <a name="client"></a><span data-ttu-id="fc0d8-101">\<client></span><span class="sxs-lookup"><span data-stu-id="fc0d8-101">\<client></span></span>
<span data-ttu-id="fc0d8-102">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
<span data-ttu-id="fc0d8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc0d8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc0d8-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc0d8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fc0d8-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<> de cliente**</span><span class="sxs-lookup"><span data-stu-id="fc0d8-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0d8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc0d8-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc0d8-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc0d8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fc0d8-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc0d8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc0d8-109">Attributes</span></span>  
 <span data-ttu-id="fc0d8-110">None</span><span class="sxs-lookup"><span data-stu-id="fc0d8-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc0d8-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc0d8-111">Child Elements</span></span>  
  
|<span data-ttu-id="fc0d8-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc0d8-112">Element</span></span>|<span data-ttu-id="fc0d8-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc0d8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc0d8-114">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="fc0d8-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="fc0d8-115">Contiene una colección de elementos de extremo, que especifica los extremos a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="fc0d8-116">\<metadata></span><span class="sxs-lookup"><span data-stu-id="fc0d8-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="fc0d8-117">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc0d8-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc0d8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fc0d8-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc0d8-119">Element</span></span>|<span data-ttu-id="fc0d8-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc0d8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc0d8-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fc0d8-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="fc0d8-122">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fc0d8-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc0d8-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc0d8-123">Remarks</span></span>  
 <span data-ttu-id="fc0d8-124">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="fc0d8-125">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="fc0d8-126">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="fc0d8-127">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="fc0d8-128">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="fc0d8-129">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="fc0d8-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc0d8-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc0d8-130">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc0d8-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc0d8-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="fc0d8-132">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="fc0d8-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="fc0d8-133">Clientes</span><span class="sxs-lookup"><span data-stu-id="fc0d8-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
