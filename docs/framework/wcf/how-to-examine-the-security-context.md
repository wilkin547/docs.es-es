---
description: 'Más información acerca de cómo: examinar el contexto de seguridad'
title: Procedimiento para examinar el contexto de seguridad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: e82491a877cf1f741767c91d1e7c304ba7676e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779405"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="46ee8-103">Procedimiento para examinar el contexto de seguridad</span><span class="sxs-lookup"><span data-stu-id="46ee8-103">How to: Examine the Security Context</span></span>

<span data-ttu-id="46ee8-104">Al programar servicios Windows Communication Foundation (WCF), el contexto de seguridad del servicio le permite determinar los detalles sobre las credenciales del cliente y las notificaciones que se usan para autenticarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="46ee8-104">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="46ee8-105">Esto se hace utilizando las propiedades de la clase <xref:System.ServiceModel.ServiceSecurityContext>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-105">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="46ee8-106">Por ejemplo, puede recuperar la identidad del cliente actual utilizando la propiedad <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> o <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-106">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="46ee8-107">Para determinar si el cliente es anónimo, utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-107">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="46ee8-108">También puede determinar qué demandas se están realizando en nombre del cliente recorriendo en iteraciones la colección de demandas en la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-108">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="46ee8-109">Obtención del contexto de seguridad actual</span><span class="sxs-lookup"><span data-stu-id="46ee8-109">To get the current security context</span></span>  
  
- <span data-ttu-id="46ee8-110">Tenga acceso a la propiedad estática <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para obtener el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="46ee8-110">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="46ee8-111">Examine cualquiera de las propiedades del contexto actual de la referencia.</span><span class="sxs-lookup"><span data-stu-id="46ee8-111">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="46ee8-112">Determinación de la identidad del llamador</span><span class="sxs-lookup"><span data-stu-id="46ee8-112">To determine the identity of the caller</span></span>  
  
1. <span data-ttu-id="46ee8-113">Imprima el valor de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-113">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="46ee8-114">Análisis de las demandas de un llamador</span><span class="sxs-lookup"><span data-stu-id="46ee8-114">To parse the claims of a caller</span></span>  
  
1. <span data-ttu-id="46ee8-115">Devuelva la clase <xref:System.IdentityModel.Policy.AuthorizationContext> actual.</span><span class="sxs-lookup"><span data-stu-id="46ee8-115">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="46ee8-116">Utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para devolver el contexto de seguridad de servicio actual, a continuación, devuelva el `AuthorizationContext` mediante la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-116">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2. <span data-ttu-id="46ee8-117">Analice la colección de objetos de vueltos de <xref:System.IdentityModel.Claims.ClaimSet> mediante la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="46ee8-117">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ee8-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46ee8-118">Example</span></span>  

 <span data-ttu-id="46ee8-119">El ejemplo siguiente imprime los valores de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> del contexto de seguridad actual y la propiedad <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, el valor de recurso de la demanda, y la propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de cada demanda en el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="46ee8-119">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46ee8-120">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="46ee8-120">Compiling the Code</span></span>  

 <span data-ttu-id="46ee8-121">El código utiliza los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="46ee8-121">The code uses the following namespaces:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="46ee8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="46ee8-122">See also</span></span>

- [<span data-ttu-id="46ee8-123">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="46ee8-123">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="46ee8-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="46ee8-124">Service Identity and Authentication</span></span>](./feature-details/service-identity-and-authentication.md)
