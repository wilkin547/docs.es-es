---
description: 'Más información acerca de: <rsa>'
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 5e558e608ec1196081166d01415e12fb2c3083b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786881"
---
# \<rsa>

<span data-ttu-id="76535-102">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="76535-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="76535-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76535-103">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76535-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76535-104">Attributes and Elements</span></span>  

 <span data-ttu-id="76535-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76535-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76535-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="76535-106">Attributes</span></span>  
  
|<span data-ttu-id="76535-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="76535-107">Attribute</span></span>|<span data-ttu-id="76535-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="76535-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76535-109">value</span><span class="sxs-lookup"><span data-stu-id="76535-109">value</span></span>|<span data-ttu-id="76535-110">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="76535-110">Optional String.</span></span> <span data-ttu-id="76535-111">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="76535-111">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76535-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76535-112">Child Elements</span></span>  

 <span data-ttu-id="76535-113">None</span><span class="sxs-lookup"><span data-stu-id="76535-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76535-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76535-114">Parent Elements</span></span>  
  
|<span data-ttu-id="76535-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="76535-115">Element</span></span>|<span data-ttu-id="76535-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="76535-116">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="76535-117">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="76535-117">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76535-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76535-118">Remarks</span></span>  

 <span data-ttu-id="76535-119">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="76535-119">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="76535-120">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="76535-120">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="76535-121">Para obtener más información sobre cómo usar la identidad para validar un servicio para un cliente, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="76535-121">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76535-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76535-122">Example</span></span>  

 <span data-ttu-id="76535-123">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="76535-123">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="76535-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="76535-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="76535-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="76535-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
