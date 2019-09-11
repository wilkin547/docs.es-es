---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854826"
---
# <a name="userprincipalname"></a><span data-ttu-id="0d2c0-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="0d2c0-101">\<userPrincipalName></span></span>
<span data-ttu-id="0d2c0-102">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="0d2c0-103">Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c0-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="0d2c0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0d2c0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0d2c0-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0d2c0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0d2c0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="0d2c0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="0d2c0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="0d2c0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="0d2c0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de identidad**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="0d2c0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="0d2c0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="0d2c0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d2c0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d2c0-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d2c0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0d2c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0d2c0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0d2c0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d2c0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0d2c0-113">Attributes</span></span>  
  
|<span data-ttu-id="0d2c0-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0d2c0-114">Attribute</span></span>|<span data-ttu-id="0d2c0-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0d2c0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d2c0-116">valor</span><span class="sxs-lookup"><span data-stu-id="0d2c0-116">value</span></span>|<span data-ttu-id="0d2c0-117">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="0d2c0-118">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="0d2c0-119">El formato es: someone@example.com (como para una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="0d2c0-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d2c0-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d2c0-120">Child Elements</span></span>  
 <span data-ttu-id="0d2c0-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d2c0-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0d2c0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0d2c0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d2c0-123">Element</span></span>|<span data-ttu-id="0d2c0-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0d2c0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d2c0-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="0d2c0-125">\<identity></span></span>](identity.md)|<span data-ttu-id="0d2c0-126">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d2c0-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d2c0-127">Remarks</span></span>  
 <span data-ttu-id="0d2c0-128">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el UPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d2c0-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d2c0-129">Example</span></span>  
 <span data-ttu-id="0d2c0-130">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="0d2c0-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="0d2c0-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d2c0-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="0d2c0-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="0d2c0-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0d2c0-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="0d2c0-133">\<identity></span></span>](identity.md)
