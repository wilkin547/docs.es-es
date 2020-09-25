---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 347a08a35ff898ab7037c11d3c87fda73c3ab2ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178107"
---
# \<headers>

<span data-ttu-id="abe82-101">Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico.</span><span class="sxs-lookup"><span data-stu-id="abe82-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="abe82-102">Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.</span><span class="sxs-lookup"><span data-stu-id="abe82-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="abe82-103">Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.</span><span class="sxs-lookup"><span data-stu-id="abe82-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="abe82-104">Las entradas en la colección de encabezado de punto de conexión son los elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="abe82-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="abe82-105">Cada elemento tiene que ser XML correcto.</span><span class="sxs-lookup"><span data-stu-id="abe82-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="abe82-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abe82-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abe82-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="abe82-107">Attributes and Elements</span></span>  

 <span data-ttu-id="abe82-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="abe82-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abe82-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="abe82-109">Attributes</span></span>  

 <span data-ttu-id="abe82-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="abe82-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="abe82-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="abe82-111">Child Elements</span></span>  

 <span data-ttu-id="abe82-112">Elementos XML definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="abe82-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abe82-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="abe82-113">Parent Elements</span></span>  
  
|<span data-ttu-id="abe82-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="abe82-114">Element</span></span>|<span data-ttu-id="abe82-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="abe82-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="abe82-116">Configura tipos diferentes de extremos.</span><span class="sxs-lookup"><span data-stu-id="abe82-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abe82-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="abe82-117">Remarks</span></span>  

 <span data-ttu-id="abe82-118">Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="abe82-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="abe82-119">Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.</span><span class="sxs-lookup"><span data-stu-id="abe82-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe82-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abe82-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="abe82-121">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="abe82-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
