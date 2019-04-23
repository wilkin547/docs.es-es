---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122881"
---
# <a name="localissuer"></a><span data-ttu-id="06ede-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="06ede-101">\<localIssuer></span></span>
<span data-ttu-id="06ede-102">Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="06ede-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="06ede-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06ede-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="06ede-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="06ede-104">\<behaviors></span></span>  
<span data-ttu-id="06ede-105">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="06ede-105">endpointBehaviors section</span></span>  
<span data-ttu-id="06ede-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="06ede-106">\<behavior></span></span>  
<span data-ttu-id="06ede-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="06ede-107">\<clientCredentials></span></span>  
<span data-ttu-id="06ede-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="06ede-108">\<issuedToken></span></span>  
<span data-ttu-id="06ede-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="06ede-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ede-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06ede-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06ede-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06ede-111">Attributes and Elements</span></span>  
 <span data-ttu-id="06ede-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06ede-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06ede-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="06ede-113">Attributes</span></span>  
  
|<span data-ttu-id="06ede-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="06ede-114">Attribute</span></span>|<span data-ttu-id="06ede-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="06ede-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06ede-116">dirección</span><span class="sxs-lookup"><span data-stu-id="06ede-116">address</span></span>|<span data-ttu-id="06ede-117">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="06ede-117">Required string.</span></span> <span data-ttu-id="06ede-118">Especifica el URI del emisor local.</span><span class="sxs-lookup"><span data-stu-id="06ede-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="06ede-119">enlace</span><span class="sxs-lookup"><span data-stu-id="06ede-119">binding</span></span>|<span data-ttu-id="06ede-120">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="06ede-120">Optional string.</span></span> <span data-ttu-id="06ede-121">Uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="06ede-121">One of the system-provided bindings.</span></span> <span data-ttu-id="06ede-122">Para obtener una lista, consulte [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="06ede-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="06ede-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="06ede-123">bindingConfiguration</span></span>|<span data-ttu-id="06ede-124">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="06ede-124">Optional string.</span></span> <span data-ttu-id="06ede-125">Especifica una configuración de enlace situada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="06ede-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06ede-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06ede-126">Child Elements</span></span>  
  
|<span data-ttu-id="06ede-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="06ede-127">Element</span></span>|<span data-ttu-id="06ede-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="06ede-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06ede-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="06ede-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="06ede-130">Especifica la información de identidad para el emisor local.</span><span class="sxs-lookup"><span data-stu-id="06ede-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="06ede-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="06ede-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="06ede-132">Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente.</span><span class="sxs-lookup"><span data-stu-id="06ede-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="06ede-133">Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.</span><span class="sxs-lookup"><span data-stu-id="06ede-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06ede-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06ede-134">Parent Elements</span></span>  
  
|<span data-ttu-id="06ede-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="06ede-135">Element</span></span>|<span data-ttu-id="06ede-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="06ede-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06ede-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="06ede-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="06ede-138">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="06ede-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ede-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06ede-139">Remarks</span></span>  
 <span data-ttu-id="06ede-140">Al obtener un token emitido de un Servicio de token de seguridad  (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS.</span><span class="sxs-lookup"><span data-stu-id="06ede-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="06ede-141">Cuando el <xref:System.ServiceModel.WSFederationHttpBinding> no proporciona una dirección URL para el servicio de token de seguridad o la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, el canal de cliente Windows Communication Foundation (WCF) utiliza los valores especificados por `address`y `binding` para comunicarse con STS a fin de obtener el token emitido.</span><span class="sxs-lookup"><span data-stu-id="06ede-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="06ede-142">Para obtener más información sobre cómo configurar un emisor local, vea [Cómo: Configurar un emisor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="06ede-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ede-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06ede-143">Example</span></span>  
 <span data-ttu-id="06ede-144">El ejemplo siguiente establece `address`, `binding`y atributos `bindingConfiguration` de un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="06ede-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06ede-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="06ede-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="06ede-146">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="06ede-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="06ede-147">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="06ede-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="06ede-148">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="06ede-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="06ede-149">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="06ede-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="06ede-150">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="06ede-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="06ede-151">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="06ede-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="06ede-152">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="06ede-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="06ede-153">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="06ede-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="06ede-154">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="06ede-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
