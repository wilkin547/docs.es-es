---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940510"
---
# <a name="userprincipalname"></a><span data-ttu-id="1ef31-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="1ef31-101">\<userPrincipalName></span></span>
<span data-ttu-id="1ef31-102">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef31-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="1ef31-103">Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1ef31-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="1ef31-104">\<> de identidad</span><span class="sxs-lookup"><span data-stu-id="1ef31-104">\<identity></span></span>  
<span data-ttu-id="1ef31-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="1ef31-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef31-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ef31-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ef31-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ef31-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1ef31-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ef31-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ef31-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ef31-109">Attributes</span></span>  
  
|<span data-ttu-id="1ef31-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ef31-110">Attribute</span></span>|<span data-ttu-id="1ef31-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1ef31-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ef31-112">valor</span><span class="sxs-lookup"><span data-stu-id="1ef31-112">value</span></span>|<span data-ttu-id="1ef31-113">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1ef31-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="1ef31-114">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ef31-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="1ef31-115">El formato es: someone@example.com (como para una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="1ef31-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ef31-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ef31-116">Child Elements</span></span>  
 <span data-ttu-id="1ef31-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1ef31-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ef31-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ef31-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ef31-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ef31-119">Element</span></span>|<span data-ttu-id="1ef31-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1ef31-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ef31-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="1ef31-121">\<identity></span></span>](identity.md)|<span data-ttu-id="1ef31-122">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef31-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ef31-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ef31-123">Remarks</span></span>  
 <span data-ttu-id="1ef31-124">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el UPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1ef31-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef31-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ef31-125">Example</span></span>  
 <span data-ttu-id="1ef31-126">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef31-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="1ef31-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef31-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="1ef31-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="1ef31-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1ef31-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="1ef31-129">\<identity></span></span>](identity.md)
