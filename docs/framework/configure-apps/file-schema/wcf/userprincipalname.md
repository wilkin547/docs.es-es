---
description: 'Más información acerca de: <userPrincipalName>'
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 73ace3d6f3d5cb88f2630a4a2ae319decf420021
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664423"
---
# \<userPrincipalName>

<span data-ttu-id="31b18-102">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="31b18-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="31b18-103">Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="31b18-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="31b18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31b18-104">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31b18-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31b18-105">Attributes and Elements</span></span>  

 <span data-ttu-id="31b18-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31b18-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31b18-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="31b18-107">Attributes</span></span>  
  
|<span data-ttu-id="31b18-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="31b18-108">Attribute</span></span>|<span data-ttu-id="31b18-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="31b18-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31b18-110">value</span><span class="sxs-lookup"><span data-stu-id="31b18-110">value</span></span>|<span data-ttu-id="31b18-111">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="31b18-111">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="31b18-112">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="31b18-112">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="31b18-113">El formato es: someone@example.com (como para una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="31b18-113">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31b18-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31b18-114">Child Elements</span></span>  

 <span data-ttu-id="31b18-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="31b18-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31b18-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31b18-116">Parent Elements</span></span>  
  
|<span data-ttu-id="31b18-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="31b18-117">Element</span></span>|<span data-ttu-id="31b18-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="31b18-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="31b18-119">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="31b18-119">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31b18-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31b18-120">Remarks</span></span>  

 <span data-ttu-id="31b18-121">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el UPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="31b18-121">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b18-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31b18-122">Example</span></span>  

 <span data-ttu-id="31b18-123">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="31b18-123">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="31b18-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b18-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="31b18-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="31b18-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
