---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397862"
---
# <a name="localissuer"></a><span data-ttu-id="cfce7-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="cfce7-101">\<localIssuer></span></span>
<span data-ttu-id="cfce7-102">Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cfce7-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="cfce7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfce7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cfce7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="cfce7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="cfce7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="cfce7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="cfce7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedToken**](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="cfce7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="cfce7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> localIssuer**</span><span class="sxs-lookup"><span data-stu-id="cfce7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfce7-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfce7-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfce7-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cfce7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cfce7-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cfce7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfce7-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="cfce7-114">Attributes</span></span>  
  
|<span data-ttu-id="cfce7-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="cfce7-115">Attribute</span></span>|<span data-ttu-id="cfce7-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfce7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfce7-117">dirección</span><span class="sxs-lookup"><span data-stu-id="cfce7-117">address</span></span>|<span data-ttu-id="cfce7-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="cfce7-118">Required string.</span></span> <span data-ttu-id="cfce7-119">Especifica el URI del emisor local.</span><span class="sxs-lookup"><span data-stu-id="cfce7-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="cfce7-120">enlace</span><span class="sxs-lookup"><span data-stu-id="cfce7-120">binding</span></span>|<span data-ttu-id="cfce7-121">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="cfce7-121">Optional string.</span></span> <span data-ttu-id="cfce7-122">Uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="cfce7-122">One of the system-provided bindings.</span></span> <span data-ttu-id="cfce7-123">Para obtener una lista, vea [enlaces proporcionados](../../../wcf/system-provided-bindings.md)por el sistema.</span><span class="sxs-lookup"><span data-stu-id="cfce7-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="cfce7-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfce7-124">bindingConfiguration</span></span>|<span data-ttu-id="cfce7-125">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="cfce7-125">Optional string.</span></span> <span data-ttu-id="cfce7-126">Especifica una configuración de enlace situada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="cfce7-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfce7-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cfce7-127">Child Elements</span></span>  
  
|<span data-ttu-id="cfce7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfce7-128">Element</span></span>|<span data-ttu-id="cfce7-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfce7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfce7-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="cfce7-130">\<identity></span></span>](identity.md)|<span data-ttu-id="cfce7-131">Especifica la información de identidad para el emisor local.</span><span class="sxs-lookup"><span data-stu-id="cfce7-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="cfce7-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="cfce7-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="cfce7-133">Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente.</span><span class="sxs-lookup"><span data-stu-id="cfce7-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="cfce7-134">Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.</span><span class="sxs-lookup"><span data-stu-id="cfce7-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfce7-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cfce7-135">Parent Elements</span></span>  
  
|<span data-ttu-id="cfce7-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfce7-136">Element</span></span>|<span data-ttu-id="cfce7-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfce7-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfce7-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="cfce7-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="cfce7-139">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="cfce7-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfce7-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfce7-140">Remarks</span></span>  
 <span data-ttu-id="cfce7-141">Al obtener un token emitido de un Servicio de token de seguridad  (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS.</span><span class="sxs-lookup"><span data-stu-id="cfce7-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="cfce7-142">Cuando no proporciona una dirección URL para el servicio de token de seguridad, o cuando la dirección del emisor de un enlace federado `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` es `null`o, el canal de Windows Communication Foundation (WCF) del cliente usa los valores especificados por. <xref:System.ServiceModel.WSFederationHttpBinding> `address` y`binding` para comunicarse con el STS para obtener el token emitido.</span><span class="sxs-lookup"><span data-stu-id="cfce7-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="cfce7-143">Para obtener más información sobre la configuración de un emisor local [, consulte Cómo: Configurar un emisor](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)local.</span><span class="sxs-lookup"><span data-stu-id="cfce7-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfce7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfce7-144">Example</span></span>  
 <span data-ttu-id="cfce7-145">El ejemplo siguiente establece `address`, `binding`y atributos `bindingConfiguration` de un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="cfce7-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cfce7-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfce7-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="cfce7-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="cfce7-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="cfce7-148">Cómo: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="cfce7-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="cfce7-149">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="cfce7-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cfce7-150">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="cfce7-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="cfce7-151">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="cfce7-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cfce7-152">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cfce7-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cfce7-153">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="cfce7-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="cfce7-154">Cómo: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="cfce7-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="cfce7-155">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="cfce7-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
