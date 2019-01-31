---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 126a6923469580d2d9481ab4b999560d9beda398
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273574"
---
# <a name="rsa"></a><span data-ttu-id="b0cd2-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="b0cd2-101">\<rsa></span></span>
<span data-ttu-id="b0cd2-102">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="b0cd2-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="b0cd2-103">\<identity></span></span>  
<span data-ttu-id="b0cd2-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="b0cd2-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cd2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0cd2-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0cd2-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0cd2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b0cd2-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0cd2-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0cd2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0cd2-108">Attributes</span></span>  
  
|<span data-ttu-id="b0cd2-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0cd2-109">Attribute</span></span>|<span data-ttu-id="b0cd2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0cd2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0cd2-111">value</span><span class="sxs-lookup"><span data-stu-id="b0cd2-111">value</span></span>|<span data-ttu-id="b0cd2-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-112">Optional String.</span></span> <span data-ttu-id="b0cd2-113">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0cd2-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0cd2-114">Child Elements</span></span>  
 <span data-ttu-id="b0cd2-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b0cd2-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0cd2-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0cd2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b0cd2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0cd2-117">Element</span></span>|<span data-ttu-id="b0cd2-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0cd2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0cd2-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="b0cd2-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b0cd2-120">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0cd2-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0cd2-121">Remarks</span></span>  
 <span data-ttu-id="b0cd2-122">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="b0cd2-123">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="b0cd2-124">Para obtener más información sobre el uso de identidad para validar un servicio a un cliente, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b0cd2-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0cd2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0cd2-125">Example</span></span>  
 <span data-ttu-id="b0cd2-126">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="b0cd2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0cd2-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="b0cd2-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="b0cd2-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b0cd2-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="b0cd2-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
