---
title: <issuerChannelBehaviors> (Elemento)
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929926"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="f55e0-102">\<issuerChannelBehaviors >, elemento</span><span class="sxs-lookup"><span data-stu-id="f55e0-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="f55e0-103">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) (definidos en la configuración) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="f55e0-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="f55e0-104">Los comportamientos definidos no pueden incluir [ \<elementos > clientCredentials](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="f55e0-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="f55e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f55e0-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f55e0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f55e0-106">Attributes and Elements</span></span>

<span data-ttu-id="f55e0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f55e0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f55e0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f55e0-108">Attributes</span></span>

<span data-ttu-id="f55e0-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f55e0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f55e0-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f55e0-110">Child Elements</span></span>

|<span data-ttu-id="f55e0-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f55e0-111">Element</span></span>|<span data-ttu-id="f55e0-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f55e0-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f55e0-113">\<add></span><span class="sxs-lookup"><span data-stu-id="f55e0-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="f55e0-114">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="f55e0-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f55e0-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f55e0-115">Parent Elements</span></span>

|<span data-ttu-id="f55e0-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f55e0-116">Element</span></span>|<span data-ttu-id="f55e0-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f55e0-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f55e0-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="f55e0-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="f55e0-119">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="f55e0-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f55e0-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f55e0-120">Remarks</span></span>

<span data-ttu-id="f55e0-121">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="f55e0-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="f55e0-122">Por ejemplo, si se [ \<](datacontractserializer-element.md) debe incluir un elemento de comportamiento dataContractSerializer >.</span><span class="sxs-lookup"><span data-stu-id="f55e0-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="f55e0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f55e0-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="f55e0-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f55e0-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f55e0-125">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f55e0-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f55e0-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f55e0-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f55e0-127">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f55e0-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f55e0-128">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f55e0-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f55e0-129">Procedimientos: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="f55e0-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f55e0-130">Cómo: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="f55e0-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f55e0-131">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f55e0-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
