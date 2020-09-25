---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 353d3e2d88e3515e54deadab85c37ce3be26ef29
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203870"
---
# \<userPrincipalName>

<span data-ttu-id="b7062-101">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b7062-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="b7062-102">Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b7062-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="b7062-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7062-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7062-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7062-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b7062-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7062-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7062-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7062-106">Attributes</span></span>  
  
|<span data-ttu-id="b7062-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="b7062-107">Attribute</span></span>|<span data-ttu-id="b7062-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7062-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7062-109">value</span><span class="sxs-lookup"><span data-stu-id="b7062-109">value</span></span>|<span data-ttu-id="b7062-110">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="b7062-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="b7062-111">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7062-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="b7062-112">El formato es: someone@example.com (como para una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="b7062-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7062-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7062-113">Child Elements</span></span>  

 <span data-ttu-id="b7062-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7062-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7062-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7062-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b7062-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7062-116">Element</span></span>|<span data-ttu-id="b7062-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7062-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="b7062-118">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b7062-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7062-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7062-119">Remarks</span></span>  

 <span data-ttu-id="b7062-120">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el UPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b7062-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7062-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7062-121">Example</span></span>  

 <span data-ttu-id="b7062-122">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b7062-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="b7062-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7062-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="b7062-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="b7062-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
