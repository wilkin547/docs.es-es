---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 2e0352efdd5b709984338fe4484b120bddb7d545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704302"
---
# <a name="client"></a><span data-ttu-id="1f1cb-101">\<client></span><span class="sxs-lookup"><span data-stu-id="1f1cb-101">\<client></span></span>
<span data-ttu-id="1f1cb-102">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="1f1cb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1f1cb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1f1cb-104">\<client></span><span class="sxs-lookup"><span data-stu-id="1f1cb-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f1cb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f1cb-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f1cb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1f1cb-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1f1cb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f1cb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f1cb-108">Attributes</span></span>  
 <span data-ttu-id="1f1cb-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1f1cb-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1f1cb-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1f1cb-110">Child Elements</span></span>  
  
|<span data-ttu-id="1f1cb-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f1cb-111">Element</span></span>|<span data-ttu-id="1f1cb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f1cb-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f1cb-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="1f1cb-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="1f1cb-114">Contiene una colección de elementos de extremo, que especifica los extremos a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="1f1cb-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="1f1cb-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="1f1cb-116">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f1cb-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1f1cb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1f1cb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f1cb-118">Element</span></span>|<span data-ttu-id="1f1cb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f1cb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f1cb-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1f1cb-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="1f1cb-121">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1f1cb-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f1cb-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f1cb-122">Remarks</span></span>  
 <span data-ttu-id="1f1cb-123">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="1f1cb-124">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="1f1cb-125">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="1f1cb-126">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="1f1cb-127">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="1f1cb-128">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="1f1cb-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f1cb-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f1cb-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f1cb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f1cb-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="1f1cb-131">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="1f1cb-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1f1cb-132">Clientes</span><span class="sxs-lookup"><span data-stu-id="1f1cb-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
