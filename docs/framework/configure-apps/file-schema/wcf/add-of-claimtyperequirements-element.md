---
title: <add>de <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153105"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="dd4e6-102">\<agregar> \<de elemento> claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="dd4e6-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="dd4e6-103">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="dd4e6-104">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="dd4e6-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd4e6-106">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dd4e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<encuadernaciones>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="dd4e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="dd4e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enlace>**</span><span class="sxs-lookup"><span data-stu-id="dd4e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dd4e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>de seguridad**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="dd4e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<mensaje>**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="dd4e6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="dd4e6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="dd4e6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="dd4e6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="dd4e6-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd4e6-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd4e6-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dd4e6-115">Attributes and Elements</span></span>  
 <span data-ttu-id="dd4e6-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd4e6-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd4e6-117">Attributes</span></span>  
  
|<span data-ttu-id="dd4e6-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="dd4e6-118">Attribute</span></span>|<span data-ttu-id="dd4e6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd4e6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd4e6-120">claimType</span><span class="sxs-lookup"><span data-stu-id="dd4e6-120">claimType</span></span>|<span data-ttu-id="dd4e6-121">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="dd4e6-122">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="dd4e6-123">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="dd4e6-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="dd4e6-124">isOptional</span></span>|<span data-ttu-id="dd4e6-125">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="dd4e6-126">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="dd4e6-127">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="dd4e6-128">Por ejemplo, si necesita que el usuario escriba su nombre, apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd4e6-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dd4e6-129">Child Elements</span></span>  
 <span data-ttu-id="dd4e6-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd4e6-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dd4e6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="dd4e6-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd4e6-132">Element</span></span>|<span data-ttu-id="dd4e6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd4e6-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd4e6-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="dd4e6-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="dd4e6-135">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="dd4e6-136">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="dd4e6-137">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dd4e6-138">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dd4e6-139">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd4e6-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd4e6-140">Remarks</span></span>  
 <span data-ttu-id="dd4e6-141">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dd4e6-142">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dd4e6-143">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="dd4e6-144">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd4e6-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd4e6-145">Example</span></span>  
 <span data-ttu-id="dd4e6-146">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd4e6-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd4e6-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
