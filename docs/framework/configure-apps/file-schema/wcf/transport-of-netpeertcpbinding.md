---
description: 'Más información sobre: <transport> de <netPeerTcpBinding>'
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: e93885234577e4f3c7a99be66e4798d33ffb5893
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664579"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="d626b-103">\<transport> de \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d626b-103">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="d626b-104">Especifica la configuración de seguridad de nivel de transporte cuando se usa [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d626b-104">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="d626b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d626b-105">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d626b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d626b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d626b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d626b-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d626b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d626b-108">Attributes</span></span>  
  
|<span data-ttu-id="d626b-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="d626b-109">Attribute</span></span>|<span data-ttu-id="d626b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d626b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d626b-111">credentialType</span><span class="sxs-lookup"><span data-stu-id="d626b-111">credentialType</span></span>|<span data-ttu-id="d626b-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d626b-112">Optional.</span></span> <span data-ttu-id="d626b-113">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d626b-113">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="d626b-114">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d626b-114">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="d626b-115">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="d626b-115">credentialType Attribute</span></span>  
  
|<span data-ttu-id="d626b-116">Value</span><span class="sxs-lookup"><span data-stu-id="d626b-116">Value</span></span>|<span data-ttu-id="d626b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d626b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d626b-118">Certificado</span><span class="sxs-lookup"><span data-stu-id="d626b-118">Certificate</span></span>|<span data-ttu-id="d626b-119">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="d626b-119">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="d626b-120">Contraseña</span><span class="sxs-lookup"><span data-stu-id="d626b-120">Password</span></span>|<span data-ttu-id="d626b-121">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="d626b-121">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d626b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d626b-122">Child Elements</span></span>  

 <span data-ttu-id="d626b-123">None</span><span class="sxs-lookup"><span data-stu-id="d626b-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d626b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d626b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d626b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d626b-125">Element</span></span>|<span data-ttu-id="d626b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="d626b-126">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="d626b-127">Define la configuración de seguridad para [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d626b-127">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d626b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d626b-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="d626b-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d626b-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d626b-130">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d626b-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d626b-131">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d626b-131">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d626b-132">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d626b-132">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
