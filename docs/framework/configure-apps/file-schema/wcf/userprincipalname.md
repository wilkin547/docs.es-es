---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: ff38a6975d1ec73c1a3014b94198ba630c3fec31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149985"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="29c31-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="29c31-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="29c31-103">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="29c31-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="29c31-104">Para obtener más información acerca de cómo establecer el UPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="29c31-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="29c31-105">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="29c31-105">\<identity></span></span>  
<span data-ttu-id="29c31-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="29c31-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c31-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29c31-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29c31-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29c31-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29c31-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29c31-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29c31-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="29c31-110">Attributes</span></span>  
  
|<span data-ttu-id="29c31-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="29c31-111">Attribute</span></span>|<span data-ttu-id="29c31-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="29c31-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29c31-113">value</span><span class="sxs-lookup"><span data-stu-id="29c31-113">value</span></span>|<span data-ttu-id="29c31-114">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="29c31-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="29c31-115">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="29c31-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="29c31-116">El formato es: someone@example.com (como en una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="29c31-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29c31-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29c31-117">Child Elements</span></span>  
 <span data-ttu-id="29c31-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29c31-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29c31-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29c31-119">Parent Elements</span></span>  
  
|<span data-ttu-id="29c31-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="29c31-120">Element</span></span>|<span data-ttu-id="29c31-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="29c31-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29c31-122">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="29c31-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="29c31-123">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="29c31-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29c31-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29c31-124">Remarks</span></span>  
 <span data-ttu-id="29c31-125">Un cliente segura de Windows Communication Foundation (WCF) que se conecta a un punto de conexión con esta identidad utiliza UPN al realizar la autenticación de SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="29c31-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29c31-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29c31-126">Example</span></span>  
 <span data-ttu-id="29c31-127">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="29c31-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="29c31-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="29c31-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="29c31-129">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="29c31-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="29c31-130">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="29c31-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
