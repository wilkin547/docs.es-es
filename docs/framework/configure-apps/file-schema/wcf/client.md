---
title: '&lt;cliente&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d52d74c36ea1b1d722d781f554f8cc6691d53e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="f18e0-102">&lt;cliente&gt;</span><span class="sxs-lookup"><span data-stu-id="f18e0-102">&lt;client&gt;</span></span>
<span data-ttu-id="f18e0-103">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="f18e0-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="f18e0-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f18e0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f18e0-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="f18e0-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18e0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f18e0-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f18e0-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f18e0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f18e0-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f18e0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f18e0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f18e0-109">Attributes</span></span>  
 <span data-ttu-id="f18e0-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f18e0-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f18e0-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f18e0-111">Child Elements</span></span>  
  
|<span data-ttu-id="f18e0-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f18e0-112">Element</span></span>|<span data-ttu-id="f18e0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f18e0-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f18e0-114">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="f18e0-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="f18e0-115">Contiene una colección de elementos de punto de conexión, que especifica los puntos de conexión a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="f18e0-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="f18e0-116">\<metadatos ></span><span class="sxs-lookup"><span data-stu-id="f18e0-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="f18e0-117">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="f18e0-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f18e0-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f18e0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f18e0-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f18e0-119">Element</span></span>|<span data-ttu-id="f18e0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f18e0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f18e0-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f18e0-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="f18e0-122">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f18e0-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f18e0-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f18e0-123">Remarks</span></span>  
 <span data-ttu-id="f18e0-124">La sección `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="f18e0-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="f18e0-125">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="f18e0-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="f18e0-126">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="f18e0-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="f18e0-127">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="f18e0-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="f18e0-128">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="f18e0-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="f18e0-129">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="f18e0-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f18e0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f18e0-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f18e0-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f18e0-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="f18e0-132">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="f18e0-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="f18e0-133">Clientes</span><span class="sxs-lookup"><span data-stu-id="f18e0-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
