---
title: '&lt;Cliente&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b8a006d3dee4149569b3f5b573d9d765504b0d65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752642"
---
# <a name="ltclientgt"></a><span data-ttu-id="75bf1-102">&lt;Cliente&gt;</span><span class="sxs-lookup"><span data-stu-id="75bf1-102">&lt;client&gt;</span></span>
<span data-ttu-id="75bf1-103">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="75bf1-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="75bf1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="75bf1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="75bf1-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="75bf1-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75bf1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75bf1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75bf1-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75bf1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="75bf1-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75bf1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75bf1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="75bf1-109">Attributes</span></span>  
 <span data-ttu-id="75bf1-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="75bf1-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75bf1-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75bf1-111">Child Elements</span></span>  
  
|<span data-ttu-id="75bf1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="75bf1-112">Element</span></span>|<span data-ttu-id="75bf1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75bf1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75bf1-114">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="75bf1-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="75bf1-115">Contiene una colección de elementos de punto de conexión, que especifica los puntos de conexión a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="75bf1-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="75bf1-116">\<metadatos ></span><span class="sxs-lookup"><span data-stu-id="75bf1-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="75bf1-117">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="75bf1-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75bf1-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75bf1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="75bf1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="75bf1-119">Element</span></span>|<span data-ttu-id="75bf1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="75bf1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75bf1-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="75bf1-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="75bf1-122">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="75bf1-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75bf1-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75bf1-123">Remarks</span></span>  
 <span data-ttu-id="75bf1-124">La sección `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="75bf1-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="75bf1-125">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="75bf1-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="75bf1-126">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="75bf1-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="75bf1-127">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="75bf1-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="75bf1-128">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="75bf1-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="75bf1-129">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="75bf1-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75bf1-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75bf1-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75bf1-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="75bf1-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="75bf1-132">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="75bf1-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="75bf1-133">Clientes</span><span class="sxs-lookup"><span data-stu-id="75bf1-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
