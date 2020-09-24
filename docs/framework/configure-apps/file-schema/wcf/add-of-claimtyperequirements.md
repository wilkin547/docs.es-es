---
title: <add> de <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 00699a6fa5d0de7ac554db6ef8d0bbe511a85c0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149223"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="03306-102">\<add> de \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="03306-102">\<add> of \<claimTypeRequirements></span></span>

<span data-ttu-id="03306-103">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="03306-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="03306-104">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="03306-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="03306-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03306-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03306-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03306-106">Attributes and Elements</span></span>  

 <span data-ttu-id="03306-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03306-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03306-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="03306-108">Attributes</span></span>  
  
|<span data-ttu-id="03306-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="03306-109">Attribute</span></span>|<span data-ttu-id="03306-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="03306-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03306-111">claimType</span><span class="sxs-lookup"><span data-stu-id="03306-111">claimType</span></span>|<span data-ttu-id="03306-112">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="03306-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="03306-113">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="03306-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="03306-114">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="03306-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="03306-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="03306-115">isOptional</span></span>|<span data-ttu-id="03306-116">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="03306-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="03306-117">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="03306-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="03306-118">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="03306-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="03306-119">Por ejemplo, si necesita que el usuario escriba su nombre, Apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="03306-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03306-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03306-120">Child Elements</span></span>  

 <span data-ttu-id="03306-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="03306-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03306-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03306-122">Parent Elements</span></span>  
  
|<span data-ttu-id="03306-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="03306-123">Element</span></span>|<span data-ttu-id="03306-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="03306-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="03306-125">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="03306-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="03306-126">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="03306-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="03306-127">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="03306-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="03306-128">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="03306-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03306-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03306-129">Remarks</span></span>  

 <span data-ttu-id="03306-130">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="03306-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="03306-131">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="03306-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="03306-132">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03306-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="03306-133">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="03306-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03306-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03306-134">Example</span></span>  

 <span data-ttu-id="03306-135">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03306-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03306-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="03306-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="03306-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="03306-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="03306-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="03306-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="03306-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="03306-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="03306-140">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="03306-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="03306-141">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="03306-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
