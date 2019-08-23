---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: dd8e5ab11a7c019a8fe967f1c14b88a922a16c33
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934738"
---
# <a name="rsa"></a><span data-ttu-id="e5248-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="e5248-101">\<rsa></span></span>
<span data-ttu-id="e5248-102">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="e5248-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="e5248-103">\<> de identidad</span><span class="sxs-lookup"><span data-stu-id="e5248-103">\<identity></span></span>  
<span data-ttu-id="e5248-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="e5248-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5248-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5248-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5248-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5248-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e5248-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5248-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5248-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5248-108">Attributes</span></span>  
  
|<span data-ttu-id="e5248-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5248-109">Attribute</span></span>|<span data-ttu-id="e5248-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5248-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5248-111">valor</span><span class="sxs-lookup"><span data-stu-id="e5248-111">value</span></span>|<span data-ttu-id="e5248-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="e5248-112">Optional String.</span></span> <span data-ttu-id="e5248-113">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="e5248-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5248-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5248-114">Child Elements</span></span>  
 <span data-ttu-id="e5248-115">None</span><span class="sxs-lookup"><span data-stu-id="e5248-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5248-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5248-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e5248-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5248-117">Element</span></span>|<span data-ttu-id="e5248-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5248-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5248-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="e5248-119">\<identity></span></span>](identity.md)|<span data-ttu-id="e5248-120">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="e5248-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5248-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5248-121">Remarks</span></span>  
 <span data-ttu-id="e5248-122">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="e5248-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="e5248-123">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="e5248-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="e5248-124">Para obtener más información sobre cómo usar la identidad para validar un servicio para un cliente, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e5248-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5248-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5248-125">Example</span></span>  
 <span data-ttu-id="e5248-126">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="e5248-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e5248-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5248-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="e5248-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="e5248-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e5248-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="e5248-129">\<identity></span></span>](identity.md)
