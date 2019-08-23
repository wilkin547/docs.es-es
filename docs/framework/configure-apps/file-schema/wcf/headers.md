---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: a982fa87ab84725e36ee913f00200cd34f0b8f6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925574"
---
# <a name="headers"></a><span data-ttu-id="2d894-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="2d894-101">\<headers></span></span>
<span data-ttu-id="2d894-102">Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="2d894-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="2d894-103">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="2d894-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="2d894-104">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="2d894-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="2d894-105">Las entradas en la colección de encabezado de punto de conexión son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2d894-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="2d894-106">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="2d894-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="2d894-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d894-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d894-108">\<client></span><span class="sxs-lookup"><span data-stu-id="2d894-108">\<client></span></span>  
<span data-ttu-id="2d894-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2d894-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d894-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d894-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d894-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d894-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2d894-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d894-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d894-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d894-113">Attributes</span></span>  
 <span data-ttu-id="2d894-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d894-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d894-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d894-115">Child Elements</span></span>  
 <span data-ttu-id="2d894-116">Elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2d894-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d894-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d894-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2d894-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d894-118">Element</span></span>|<span data-ttu-id="2d894-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2d894-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d894-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2d894-120">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="2d894-121">Configura tipos diferentes de extremos.</span><span class="sxs-lookup"><span data-stu-id="2d894-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d894-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d894-122">Remarks</span></span>  
 <span data-ttu-id="2d894-123">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2d894-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="2d894-124">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="2d894-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d894-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d894-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="2d894-126">Extremos Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="2d894-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
