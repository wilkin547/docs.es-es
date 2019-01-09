---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 7a48cbb3a1e17ac1fc9fa9f43301ef153cdb866c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151888"
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="9ef75-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="9ef75-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="9ef75-103">Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ef75-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="9ef75-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ef75-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ef75-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9ef75-105">\<behaviors></span></span>  
<span data-ttu-id="9ef75-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="9ef75-106">endpointBehaviors section</span></span>  
<span data-ttu-id="9ef75-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9ef75-107">\<behavior></span></span>  
<span data-ttu-id="9ef75-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9ef75-108">\<clientCredentials></span></span>  
<span data-ttu-id="9ef75-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="9ef75-109">\<issuedToken></span></span>  
<span data-ttu-id="9ef75-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="9ef75-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef75-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ef75-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ef75-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ef75-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9ef75-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ef75-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ef75-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ef75-114">Attributes</span></span>  
  
|<span data-ttu-id="9ef75-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ef75-115">Attribute</span></span>|<span data-ttu-id="9ef75-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ef75-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ef75-117">address</span><span class="sxs-lookup"><span data-stu-id="9ef75-117">address</span></span>|<span data-ttu-id="9ef75-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="9ef75-118">Required string.</span></span> <span data-ttu-id="9ef75-119">Especifica el URI del emisor local.</span><span class="sxs-lookup"><span data-stu-id="9ef75-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="9ef75-120">enlace</span><span class="sxs-lookup"><span data-stu-id="9ef75-120">binding</span></span>|<span data-ttu-id="9ef75-121">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="9ef75-121">Optional string.</span></span> <span data-ttu-id="9ef75-122">Uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="9ef75-122">One of the system-provided bindings.</span></span> <span data-ttu-id="9ef75-123">Para obtener una lista, consulte [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="9ef75-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="9ef75-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ef75-124">bindingConfiguration</span></span>|<span data-ttu-id="9ef75-125">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="9ef75-125">Optional string.</span></span> <span data-ttu-id="9ef75-126">Especifica una configuración de enlace situada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef75-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ef75-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ef75-127">Child Elements</span></span>  
  
|<span data-ttu-id="9ef75-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ef75-128">Element</span></span>|<span data-ttu-id="9ef75-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ef75-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ef75-130">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="9ef75-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9ef75-131">Especifica la información de identidad para el emisor local.</span><span class="sxs-lookup"><span data-stu-id="9ef75-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="9ef75-132">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="9ef75-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="9ef75-133">Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ef75-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="9ef75-134">Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.</span><span class="sxs-lookup"><span data-stu-id="9ef75-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ef75-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ef75-135">Parent Elements</span></span>  
  
|<span data-ttu-id="9ef75-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ef75-136">Element</span></span>|<span data-ttu-id="9ef75-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ef75-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ef75-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="9ef75-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="9ef75-139">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="9ef75-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ef75-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ef75-140">Remarks</span></span>  
 <span data-ttu-id="9ef75-141">Al obtener un token emitido de un Servicio de token de seguridad (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS.</span><span class="sxs-lookup"><span data-stu-id="9ef75-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="9ef75-142">Cuando el <xref:System.ServiceModel.WSFederationHttpBinding> no proporciona una dirección URL para el servicio de token de seguridad o la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, el canal de cliente Windows Communication Foundation (WCF) utiliza los valores especificados por `address`y `binding` para comunicarse con STS a fin de obtener el token emitido.</span><span class="sxs-lookup"><span data-stu-id="9ef75-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="9ef75-143">Para obtener más información sobre cómo configurar un emisor local, vea [Cómo: Configurar un emisor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="9ef75-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ef75-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ef75-144">Example</span></span>  
 <span data-ttu-id="9ef75-145">El ejemplo siguiente establece `address`, `binding`y atributos `bindingConfiguration` de un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="9ef75-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ef75-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ef75-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="9ef75-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ef75-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="9ef75-148">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="9ef75-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="9ef75-149">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="9ef75-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9ef75-150">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ef75-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="9ef75-151">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9ef75-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9ef75-152">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9ef75-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9ef75-153">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="9ef75-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="9ef75-154">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="9ef75-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="9ef75-155">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9ef75-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
