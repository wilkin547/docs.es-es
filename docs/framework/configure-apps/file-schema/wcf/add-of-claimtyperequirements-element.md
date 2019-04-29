---
title: <add> de <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 47eb9f95fd024b7df24a16781b3d89fe6deb0b8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701156"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="f6f6c-102">\<Agregar > de \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="f6f6c-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="f6f6c-103">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="f6f6c-104">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="f6f6c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f6f6c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6f6c-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f6f6c-106">\<bindings></span></span>  
<span data-ttu-id="f6f6c-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="f6f6c-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="f6f6c-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="f6f6c-108">\<binding></span></span>  
<span data-ttu-id="f6f6c-109">\<security></span><span class="sxs-lookup"><span data-stu-id="f6f6c-109">\<security></span></span>  
<span data-ttu-id="f6f6c-110">\<message></span><span class="sxs-lookup"><span data-stu-id="f6f6c-110">\<message></span></span>  
<span data-ttu-id="f6f6c-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="f6f6c-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f6c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6f6c-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6f6c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f6f6c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f6f6c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6f6c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="f6f6c-115">Attributes</span></span>  
  
|<span data-ttu-id="f6f6c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="f6f6c-116">Attribute</span></span>|<span data-ttu-id="f6f6c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6f6c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6f6c-118">claimType</span><span class="sxs-lookup"><span data-stu-id="f6f6c-118">claimType</span></span>|<span data-ttu-id="f6f6c-119">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="f6f6c-120">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="f6f6c-121">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="f6f6c-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="f6f6c-122">isOptional</span></span>|<span data-ttu-id="f6f6c-123">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="f6f6c-124">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="f6f6c-125">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="f6f6c-126">Por ejemplo, si le exige al usuario que escriba su nombre, apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6f6c-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f6f6c-127">Child Elements</span></span>  
 <span data-ttu-id="f6f6c-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6f6c-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f6f6c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f6f6c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6f6c-130">Element</span></span>|<span data-ttu-id="f6f6c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6f6c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6f6c-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="f6f6c-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="f6f6c-133">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="f6f6c-134">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="f6f6c-135">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f6f6c-136">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f6f6c-137">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6f6c-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f6c-138">Remarks</span></span>  
 <span data-ttu-id="f6f6c-139">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f6f6c-140">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f6f6c-141">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="f6f6c-142">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f6c-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6f6c-143">Example</span></span>  
 <span data-ttu-id="f6f6c-144">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6f6c-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="f6f6c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6f6c-145">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
