---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7dce5984882e48c3e62efc44ef00b6256d9eb64e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919528"
---
# <a name="client"></a><span data-ttu-id="21f4d-101">\<client></span><span class="sxs-lookup"><span data-stu-id="21f4d-101">\<client></span></span>
<span data-ttu-id="21f4d-102">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="21f4d-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="21f4d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="21f4d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="21f4d-104">\<client></span><span class="sxs-lookup"><span data-stu-id="21f4d-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21f4d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21f4d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21f4d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="21f4d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21f4d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21f4d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="21f4d-108">Attributes</span></span>  
 <span data-ttu-id="21f4d-109">None</span><span class="sxs-lookup"><span data-stu-id="21f4d-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="21f4d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21f4d-110">Child Elements</span></span>  
  
|<span data-ttu-id="21f4d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="21f4d-111">Element</span></span>|<span data-ttu-id="21f4d-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21f4d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21f4d-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="21f4d-113">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="21f4d-114">Contiene una colección de elementos de extremo, que especifica los extremos a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="21f4d-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="21f4d-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="21f4d-115">\<metadata></span></span>](metadata.md)|<span data-ttu-id="21f4d-116">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="21f4d-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21f4d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21f4d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="21f4d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="21f4d-118">Element</span></span>|<span data-ttu-id="21f4d-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21f4d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21f4d-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="21f4d-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="21f4d-121">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="21f4d-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21f4d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21f4d-122">Remarks</span></span>  
 <span data-ttu-id="21f4d-123">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="21f4d-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="21f4d-124">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="21f4d-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="21f4d-125">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="21f4d-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="21f4d-126">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="21f4d-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="21f4d-127">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="21f4d-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="21f4d-128">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="21f4d-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21f4d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21f4d-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21f4d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="21f4d-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="21f4d-131">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="21f4d-131">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="21f4d-132">Clientes</span><span class="sxs-lookup"><span data-stu-id="21f4d-132">Clients</span></span>](../../../wcf/feature-details/clients.md)
