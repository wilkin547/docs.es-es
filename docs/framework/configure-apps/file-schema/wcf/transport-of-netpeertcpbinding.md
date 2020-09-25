---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 5df47b1bfc149b524fc9b90eacffa832817f653c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172871"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="3e551-102">\<transport> de \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="3e551-102">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="3e551-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3e551-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3e551-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e551-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e551-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e551-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3e551-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e551-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e551-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e551-107">Attributes</span></span>  
  
|<span data-ttu-id="3e551-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e551-108">Attribute</span></span>|<span data-ttu-id="3e551-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e551-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e551-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="3e551-110">credentialType</span></span>|<span data-ttu-id="3e551-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3e551-111">Optional.</span></span> <span data-ttu-id="3e551-112">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3e551-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3e551-113">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3e551-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3e551-114">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="3e551-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3e551-115">Value</span><span class="sxs-lookup"><span data-stu-id="3e551-115">Value</span></span>|<span data-ttu-id="3e551-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e551-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e551-117">Certificado</span><span class="sxs-lookup"><span data-stu-id="3e551-117">Certificate</span></span>|<span data-ttu-id="3e551-118">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="3e551-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3e551-119">Contraseña</span><span class="sxs-lookup"><span data-stu-id="3e551-119">Password</span></span>|<span data-ttu-id="3e551-120">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="3e551-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e551-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e551-121">Child Elements</span></span>  

 <span data-ttu-id="3e551-122">None</span><span class="sxs-lookup"><span data-stu-id="3e551-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e551-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e551-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3e551-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e551-124">Element</span></span>|<span data-ttu-id="3e551-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e551-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="3e551-126">Define la configuración de seguridad para [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3e551-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e551-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e551-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="3e551-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3e551-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3e551-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3e551-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3e551-130">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3e551-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3e551-131">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3e551-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
