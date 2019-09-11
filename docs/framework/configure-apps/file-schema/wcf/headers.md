---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855174"
---
# <a name="headers"></a><span data-ttu-id="b4a29-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="b4a29-101">\<headers></span></span>
<span data-ttu-id="b4a29-102">Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="b4a29-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="b4a29-103">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="b4a29-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="b4a29-104">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="b4a29-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="b4a29-105">Las entradas en la colección de encabezado de punto de conexión son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b4a29-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="b4a29-106">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="b4a29-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="b4a29-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4a29-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4a29-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4a29-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b4a29-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="b4a29-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="b4a29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="b4a29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="b4a29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<encabezados >**</span><span class="sxs-lookup"><span data-stu-id="b4a29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a29-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4a29-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4a29-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b4a29-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b4a29-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b4a29-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4a29-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="b4a29-115">Attributes</span></span>  
 <span data-ttu-id="b4a29-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b4a29-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4a29-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b4a29-117">Child Elements</span></span>  
 <span data-ttu-id="b4a29-118">Elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b4a29-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4a29-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b4a29-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b4a29-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4a29-120">Element</span></span>|<span data-ttu-id="b4a29-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b4a29-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4a29-122">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="b4a29-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="b4a29-123">Configura tipos diferentes de extremos.</span><span class="sxs-lookup"><span data-stu-id="b4a29-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4a29-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4a29-124">Remarks</span></span>  
 <span data-ttu-id="b4a29-125">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b4a29-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="b4a29-126">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4a29-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a29-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4a29-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="b4a29-128">Extremos Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="b4a29-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
