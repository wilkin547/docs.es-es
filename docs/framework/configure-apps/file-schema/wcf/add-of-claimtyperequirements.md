---
title: <add> de <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 53da9dacbd3277bd8b608296a1515e3da7296f1c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398367"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="39dd7-102">\<Agregar > de \<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="39dd7-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="39dd7-103">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="39dd7-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="39dd7-104">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="39dd7-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="39dd7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39dd7-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39dd7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="39dd7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="39dd7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="39dd7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="39dd7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="39dd7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="39dd7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="39dd7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="39dd7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="39dd7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39dd7-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39dd7-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39dd7-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="39dd7-115">Attributes and Elements</span></span>  
 <span data-ttu-id="39dd7-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="39dd7-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39dd7-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="39dd7-117">Attributes</span></span>  
  
|<span data-ttu-id="39dd7-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="39dd7-118">Attribute</span></span>|<span data-ttu-id="39dd7-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="39dd7-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39dd7-120">claimType</span><span class="sxs-lookup"><span data-stu-id="39dd7-120">claimType</span></span>|<span data-ttu-id="39dd7-121">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="39dd7-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="39dd7-122">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="39dd7-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="39dd7-123">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="39dd7-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="39dd7-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="39dd7-124">isOptional</span></span>|<span data-ttu-id="39dd7-125">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="39dd7-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="39dd7-126">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="39dd7-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="39dd7-127">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="39dd7-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="39dd7-128">Por ejemplo, si le exige al usuario que escriba su nombre, apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="39dd7-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39dd7-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="39dd7-129">Child Elements</span></span>  
 <span data-ttu-id="39dd7-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="39dd7-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39dd7-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="39dd7-131">Parent Elements</span></span>  
  
|<span data-ttu-id="39dd7-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="39dd7-132">Element</span></span>|<span data-ttu-id="39dd7-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="39dd7-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39dd7-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="39dd7-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="39dd7-135">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="39dd7-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="39dd7-136">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="39dd7-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="39dd7-137">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="39dd7-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="39dd7-138">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="39dd7-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39dd7-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39dd7-139">Remarks</span></span>  
 <span data-ttu-id="39dd7-140">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="39dd7-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="39dd7-141">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="39dd7-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="39dd7-142">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39dd7-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="39dd7-143">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="39dd7-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39dd7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39dd7-144">Example</span></span>  
 <span data-ttu-id="39dd7-145">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39dd7-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39dd7-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="39dd7-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="39dd7-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="39dd7-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="39dd7-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="39dd7-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="39dd7-149">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="39dd7-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="39dd7-150">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="39dd7-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="39dd7-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="39dd7-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="39dd7-152">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="39dd7-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="39dd7-153">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="39dd7-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
