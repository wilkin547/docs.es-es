---
description: 'Más información acerca de: <localIssuer>'
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 38928f1bfd7740aa902de46958740a1e8fe63e5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725485"
---
# \<localIssuer>

<span data-ttu-id="7a8e4-102">Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="7a8e4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a8e4-103">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a8e4-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a8e4-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7a8e4-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a8e4-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a8e4-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a8e4-106">Attributes</span></span>  
  
|<span data-ttu-id="7a8e4-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="7a8e4-107">Attribute</span></span>|<span data-ttu-id="7a8e4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a8e4-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a8e4-109">address</span><span class="sxs-lookup"><span data-stu-id="7a8e4-109">address</span></span>|<span data-ttu-id="7a8e4-110">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-110">Required string.</span></span> <span data-ttu-id="7a8e4-111">Especifica el URI del emisor local.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-111">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="7a8e4-112">binding</span><span class="sxs-lookup"><span data-stu-id="7a8e4-112">binding</span></span>|<span data-ttu-id="7a8e4-113">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-113">Optional string.</span></span> <span data-ttu-id="7a8e4-114">Uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-114">One of the system-provided bindings.</span></span> <span data-ttu-id="7a8e4-115">Para obtener una lista, vea [enlaces proporcionados](../../../wcf/system-provided-bindings.md)por el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-115">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="7a8e4-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a8e4-116">bindingConfiguration</span></span>|<span data-ttu-id="7a8e4-117">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-117">Optional string.</span></span> <span data-ttu-id="7a8e4-118">Especifica una configuración de enlace situada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-118">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a8e4-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a8e4-119">Child Elements</span></span>  
  
|<span data-ttu-id="7a8e4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a8e4-120">Element</span></span>|<span data-ttu-id="7a8e4-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a8e4-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="7a8e4-122">Especifica la información de identidad para el emisor local.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-122">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="7a8e4-123">Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-123">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="7a8e4-124">Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-124">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a8e4-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a8e4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7a8e4-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a8e4-126">Element</span></span>|<span data-ttu-id="7a8e4-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a8e4-127">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="7a8e4-128">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-128">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a8e4-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a8e4-129">Remarks</span></span>  

 <span data-ttu-id="7a8e4-130">Al obtener un token emitido de un Servicio de token de seguridad  (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-130">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="7a8e4-131">Cuando no <xref:System.ServiceModel.WSFederationHttpBinding> proporciona una dirección URL para el servicio de token de seguridad, o cuando la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null` , el canal de Windows Communication Foundation (WCF) del cliente usa los valores especificados por `address` y `binding` para comunicarse con el STS para obtener el token emitido.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-131">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="7a8e4-132">Para obtener más información sobre la configuración de un emisor local, consulte [How to: Configure a local issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="7a8e4-132">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a8e4-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a8e4-133">Example</span></span>  

 <span data-ttu-id="7a8e4-134">El ejemplo siguiente establece `address`, `binding`y atributos `bindingConfiguration` de un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="7a8e4-134">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="7a8e4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a8e4-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="7a8e4-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="7a8e4-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7a8e4-137">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="7a8e4-137">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7a8e4-138">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="7a8e4-138">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7a8e4-139">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="7a8e4-139">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7a8e4-140">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="7a8e4-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7a8e4-141">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7a8e4-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7a8e4-142">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="7a8e4-142">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7a8e4-143">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="7a8e4-143">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7a8e4-144">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="7a8e4-144">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
