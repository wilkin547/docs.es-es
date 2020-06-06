---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855046"
---
# \<rsa>
<span data-ttu-id="361f6-101">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="361f6-101">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="361f6-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="361f6-102">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="361f6-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="361f6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="361f6-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="361f6-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="361f6-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="361f6-105">Attributes</span></span>  
  
|<span data-ttu-id="361f6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="361f6-106">Attribute</span></span>|<span data-ttu-id="361f6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="361f6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="361f6-108">value</span><span class="sxs-lookup"><span data-stu-id="361f6-108">value</span></span>|<span data-ttu-id="361f6-109">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="361f6-109">Optional String.</span></span> <span data-ttu-id="361f6-110">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="361f6-110">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="361f6-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="361f6-111">Child Elements</span></span>  
 <span data-ttu-id="361f6-112">None</span><span class="sxs-lookup"><span data-stu-id="361f6-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="361f6-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="361f6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="361f6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="361f6-114">Element</span></span>|<span data-ttu-id="361f6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="361f6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="361f6-116">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="361f6-116">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="361f6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="361f6-117">Remarks</span></span>  
 <span data-ttu-id="361f6-118">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="361f6-118">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="361f6-119">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="361f6-119">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="361f6-120">Para obtener más información sobre cómo usar la identidad para validar un servicio para un cliente, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="361f6-120">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="361f6-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="361f6-121">Example</span></span>  
 <span data-ttu-id="361f6-122">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="361f6-122">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="361f6-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="361f6-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="361f6-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="361f6-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
