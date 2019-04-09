---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188255"
---
# <a name="userprincipalname"></a><span data-ttu-id="1dd6c-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="1dd6c-101">\<userPrincipalName></span></span>
<span data-ttu-id="1dd6c-102">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="1dd6c-103">Para obtener más información acerca de cómo establecer el UPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1dd6c-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="1dd6c-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="1dd6c-104">\<identity></span></span>  
<span data-ttu-id="1dd6c-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="1dd6c-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd6c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dd6c-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dd6c-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1dd6c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1dd6c-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dd6c-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dd6c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1dd6c-109">Attributes</span></span>  
  
|<span data-ttu-id="1dd6c-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="1dd6c-110">Attribute</span></span>|<span data-ttu-id="1dd6c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dd6c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dd6c-112">value</span><span class="sxs-lookup"><span data-stu-id="1dd6c-112">value</span></span>|<span data-ttu-id="1dd6c-113">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="1dd6c-114">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="1dd6c-115">El formato es: someone@example.com (como en una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="1dd6c-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dd6c-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1dd6c-116">Child Elements</span></span>  
 <span data-ttu-id="1dd6c-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dd6c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dd6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1dd6c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dd6c-119">Element</span></span>|<span data-ttu-id="1dd6c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dd6c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dd6c-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="1dd6c-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="1dd6c-122">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dd6c-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dd6c-123">Remarks</span></span>  
 <span data-ttu-id="1dd6c-124">Un cliente segura de Windows Communication Foundation (WCF) que se conecta a un punto de conexión con esta identidad utiliza UPN al realizar la autenticación de SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dd6c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1dd6c-125">Example</span></span>  
 <span data-ttu-id="1dd6c-126">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1dd6c-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="1dd6c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dd6c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="1dd6c-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="1dd6c-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1dd6c-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="1dd6c-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
