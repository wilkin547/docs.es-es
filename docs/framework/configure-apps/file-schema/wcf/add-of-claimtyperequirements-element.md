---
description: 'Más información sobre: <add> del <claimTypeRequirements> elemento'
title: <add> del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 7ad93c4e1c2379704b38d3cdc68fddca62b3c057
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804041"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="7fa43-103">\<add> del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="7fa43-103">\<add> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="7fa43-104">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7fa43-104">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="7fa43-105">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="7fa43-105">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="7fa43-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fa43-106">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fa43-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7fa43-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7fa43-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7fa43-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fa43-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7fa43-109">Attributes</span></span>  
  
|<span data-ttu-id="7fa43-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="7fa43-110">Attribute</span></span>|<span data-ttu-id="7fa43-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fa43-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fa43-112">claimType</span><span class="sxs-lookup"><span data-stu-id="7fa43-112">claimType</span></span>|<span data-ttu-id="7fa43-113">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="7fa43-113">A URI that defines the type of a claim.</span></span> <span data-ttu-id="7fa43-114">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="7fa43-114">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="7fa43-115">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="7fa43-115">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="7fa43-116">isOptional</span><span class="sxs-lookup"><span data-stu-id="7fa43-116">isOptional</span></span>|<span data-ttu-id="7fa43-117">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="7fa43-117">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="7fa43-118">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="7fa43-118">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="7fa43-119">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="7fa43-119">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="7fa43-120">Por ejemplo, si necesita que el usuario escriba su nombre, Apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="7fa43-120">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fa43-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7fa43-121">Child Elements</span></span>  

 <span data-ttu-id="7fa43-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7fa43-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fa43-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7fa43-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7fa43-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fa43-124">Element</span></span>|<span data-ttu-id="7fa43-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fa43-125">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="7fa43-126">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="7fa43-126">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7fa43-127">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7fa43-127">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7fa43-128">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="7fa43-128">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7fa43-129">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="7fa43-129">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7fa43-130">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7fa43-130">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fa43-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7fa43-131">Remarks</span></span>  

 <span data-ttu-id="7fa43-132">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="7fa43-132">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7fa43-133">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="7fa43-133">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7fa43-134">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7fa43-134">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="7fa43-135">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="7fa43-135">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fa43-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fa43-136">Example</span></span>  

 <span data-ttu-id="7fa43-137">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7fa43-137">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7fa43-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fa43-138">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
