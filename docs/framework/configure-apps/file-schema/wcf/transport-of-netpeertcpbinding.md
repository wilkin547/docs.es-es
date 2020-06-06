---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735977"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="b5742-102">\<transport> de \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="b5742-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="b5742-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b5742-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b5742-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5742-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5742-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5742-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b5742-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5742-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5742-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5742-107">Attributes</span></span>  
  
|<span data-ttu-id="b5742-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b5742-108">Attribute</span></span>|<span data-ttu-id="b5742-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5742-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5742-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="b5742-110">credentialType</span></span>|<span data-ttu-id="b5742-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b5742-111">Optional.</span></span> <span data-ttu-id="b5742-112">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b5742-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="b5742-113">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b5742-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="b5742-114">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="b5742-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="b5742-115">Value</span><span class="sxs-lookup"><span data-stu-id="b5742-115">Value</span></span>|<span data-ttu-id="b5742-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5742-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b5742-117">Certificado</span><span class="sxs-lookup"><span data-stu-id="b5742-117">Certificate</span></span>|<span data-ttu-id="b5742-118">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="b5742-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="b5742-119">Contraseña</span><span class="sxs-lookup"><span data-stu-id="b5742-119">Password</span></span>|<span data-ttu-id="b5742-120">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="b5742-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5742-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5742-121">Child Elements</span></span>  
 <span data-ttu-id="b5742-122">None</span><span class="sxs-lookup"><span data-stu-id="b5742-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5742-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5742-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b5742-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5742-124">Element</span></span>|<span data-ttu-id="b5742-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5742-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="b5742-126">Define la configuración de seguridad para [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b5742-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5742-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5742-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="b5742-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b5742-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b5742-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b5742-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b5742-130">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b5742-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b5742-131">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b5742-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
