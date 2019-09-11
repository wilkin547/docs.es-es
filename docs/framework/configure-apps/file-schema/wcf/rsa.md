---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855046"
---
# <a name="rsa"></a><span data-ttu-id="d95ff-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="d95ff-101">\<rsa></span></span>
<span data-ttu-id="d95ff-102">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="d95ff-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="d95ff-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d95ff-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d95ff-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d95ff-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d95ff-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="d95ff-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="d95ff-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="d95ff-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="d95ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de identidad**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="d95ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="d95ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> RSA**</span><span class="sxs-lookup"><span data-stu-id="d95ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d95ff-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d95ff-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d95ff-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d95ff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d95ff-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d95ff-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d95ff-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d95ff-112">Attributes</span></span>  
  
|<span data-ttu-id="d95ff-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d95ff-113">Attribute</span></span>|<span data-ttu-id="d95ff-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d95ff-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d95ff-115">valor</span><span class="sxs-lookup"><span data-stu-id="d95ff-115">value</span></span>|<span data-ttu-id="d95ff-116">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="d95ff-116">Optional String.</span></span> <span data-ttu-id="d95ff-117">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d95ff-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d95ff-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d95ff-118">Child Elements</span></span>  
 <span data-ttu-id="d95ff-119">None</span><span class="sxs-lookup"><span data-stu-id="d95ff-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d95ff-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d95ff-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d95ff-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d95ff-121">Element</span></span>|<span data-ttu-id="d95ff-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d95ff-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d95ff-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="d95ff-123">\<identity></span></span>](identity.md)|<span data-ttu-id="d95ff-124">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="d95ff-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d95ff-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d95ff-125">Remarks</span></span>  
 <span data-ttu-id="d95ff-126">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="d95ff-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="d95ff-127">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="d95ff-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="d95ff-128">Para obtener más información sobre cómo usar la identidad para validar un servicio para un cliente, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d95ff-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d95ff-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d95ff-129">Example</span></span>  
 <span data-ttu-id="d95ff-130">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="d95ff-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="d95ff-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d95ff-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="d95ff-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d95ff-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d95ff-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="d95ff-133">\<identity></span></span>](identity.md)
