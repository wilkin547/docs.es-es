---
description: 'Más información acerca de: <headers>'
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 2a9a353823ba83b0b9672ab20c28080ee4afcb1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729854"
---
# \<headers>

<span data-ttu-id="c55af-102">Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="c55af-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="c55af-103">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="c55af-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="c55af-104">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="c55af-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="c55af-105">Las entradas en la colección de encabezado de punto de conexión son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c55af-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="c55af-106">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="c55af-106">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="c55af-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c55af-107">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c55af-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c55af-108">Attributes and Elements</span></span>  

 <span data-ttu-id="c55af-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c55af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c55af-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c55af-110">Attributes</span></span>  

 <span data-ttu-id="c55af-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c55af-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c55af-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c55af-112">Child Elements</span></span>  

 <span data-ttu-id="c55af-113">Elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c55af-113">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c55af-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c55af-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c55af-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c55af-115">Element</span></span>|<span data-ttu-id="c55af-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c55af-116">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="c55af-117">Configura tipos diferentes de extremos.</span><span class="sxs-lookup"><span data-stu-id="c55af-117">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c55af-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c55af-118">Remarks</span></span>  

 <span data-ttu-id="c55af-119">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c55af-119">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="c55af-120">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="c55af-120">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55af-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c55af-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="c55af-122">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="c55af-122">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
