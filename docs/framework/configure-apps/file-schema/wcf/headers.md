---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 3c3c3a3d747a1338e2db3afa92c735af4a588642
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288033"
---
# <a name="headers"></a><span data-ttu-id="a2315-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="a2315-101">\<headers></span></span>
<span data-ttu-id="a2315-102">Uno o más encabezados SOAP pueden direccionar un punto de conexión además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="a2315-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="a2315-103">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="a2315-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="a2315-104">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="a2315-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="a2315-105">Las entradas en la colección de encabezado de extremo son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a2315-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="a2315-106">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="a2315-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="a2315-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a2315-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2315-108">\<client></span><span class="sxs-lookup"><span data-stu-id="a2315-108">\<client></span></span>  
<span data-ttu-id="a2315-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="a2315-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2315-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2315-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2315-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a2315-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a2315-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a2315-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2315-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a2315-113">Attributes</span></span>  
 <span data-ttu-id="a2315-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a2315-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2315-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2315-115">Child Elements</span></span>  
 <span data-ttu-id="a2315-116">Elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a2315-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2315-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a2315-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a2315-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2315-118">Element</span></span>|<span data-ttu-id="a2315-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2315-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2315-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="a2315-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="a2315-121">Configura tipos diferentes de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a2315-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2315-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2315-122">Remarks</span></span>  
 <span data-ttu-id="a2315-123">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a2315-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="a2315-124">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="a2315-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2315-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2315-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="a2315-126">Puntos de conexión: Las direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="a2315-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
