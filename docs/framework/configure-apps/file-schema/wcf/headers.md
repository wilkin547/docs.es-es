---
title: '&lt;encabezados&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7fdd869553a672045c94a256b00638c9d0c4c24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="99940-102">&lt;encabezados&gt;</span><span class="sxs-lookup"><span data-stu-id="99940-102">&lt;headers&gt;</span></span>
<span data-ttu-id="99940-103">Uno o más encabezados SOAP pueden direccionar un punto de conexión además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="99940-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="99940-104">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="99940-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="99940-105">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="99940-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="99940-106">Las entradas en la colección de encabezado de extremo son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="99940-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="99940-107">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="99940-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="99940-108">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="99940-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="99940-109">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="99940-109">\<client></span></span>  
<span data-ttu-id="99940-110">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="99940-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99940-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99940-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99940-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99940-112">Attributes and Elements</span></span>  
 <span data-ttu-id="99940-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99940-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99940-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="99940-114">Attributes</span></span>  
 <span data-ttu-id="99940-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99940-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99940-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99940-116">Child Elements</span></span>  
  
|<span data-ttu-id="99940-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="99940-117">Element</span></span>|<span data-ttu-id="99940-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="99940-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99940-119">Región</span><span class="sxs-lookup"><span data-stu-id="99940-119">Region</span></span>||  
|<span data-ttu-id="99940-120">Miembro</span><span class="sxs-lookup"><span data-stu-id="99940-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="99940-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99940-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99940-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="99940-122">Element</span></span>|<span data-ttu-id="99940-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="99940-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99940-124">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="99940-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="99940-125">Configura tipos diferentes de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="99940-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99940-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99940-126">Remarks</span></span>  
 <span data-ttu-id="99940-127">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="99940-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="99940-128">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="99940-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99940-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="99940-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="99940-130">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="99940-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
