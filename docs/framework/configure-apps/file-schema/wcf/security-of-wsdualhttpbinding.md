---
description: 'Más información sobre: <security> de <wsDualHttpBinding>'
title: <security> de <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 6d2e87912aef6114d7dcb99b82e4a7804317b28a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683039"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="77950-103">\<security> de \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="77950-103">\<security> of \<wsDualHttpBinding></span></span>

<span data-ttu-id="77950-104">Define las capacidades de seguridad de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="77950-104">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="77950-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77950-105">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77950-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77950-106">Attributes and Elements</span></span>  

 <span data-ttu-id="77950-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77950-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77950-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="77950-108">Attributes</span></span>  
  
|<span data-ttu-id="77950-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="77950-109">Attribute</span></span>|<span data-ttu-id="77950-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="77950-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77950-111">mode</span><span class="sxs-lookup"><span data-stu-id="77950-111">mode</span></span>|<span data-ttu-id="77950-112">Opta.</span><span class="sxs-lookup"><span data-stu-id="77950-112">-   Optional.</span></span> <span data-ttu-id="77950-113">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="77950-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="77950-114">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="77950-114">The default value is `Message`.</span></span> <span data-ttu-id="77950-115">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="77950-115">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="77950-116">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="77950-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="77950-117">Value</span><span class="sxs-lookup"><span data-stu-id="77950-117">Value</span></span>|<span data-ttu-id="77950-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="77950-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77950-119">None</span><span class="sxs-lookup"><span data-stu-id="77950-119">None</span></span>|<span data-ttu-id="77950-120">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="77950-120">Security is disabled.</span></span>|  
|<span data-ttu-id="77950-121">Message</span><span class="sxs-lookup"><span data-stu-id="77950-121">Message</span></span>|<span data-ttu-id="77950-122">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="77950-122">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77950-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77950-123">Child Elements</span></span>  
  
|<span data-ttu-id="77950-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="77950-124">Element</span></span>|<span data-ttu-id="77950-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="77950-125">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="77950-126">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="77950-126">Defines the settings for the message-level security.</span></span> <span data-ttu-id="77950-127">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="77950-127">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77950-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77950-128">Parent Elements</span></span>  
  
|<span data-ttu-id="77950-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="77950-129">Element</span></span>|<span data-ttu-id="77950-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="77950-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="77950-131">Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="77950-131">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77950-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77950-132">Remarks</span></span>  

 <span data-ttu-id="77950-133">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="77950-133">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="77950-134">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="77950-134">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77950-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="77950-135">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="77950-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="77950-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="77950-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="77950-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="77950-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="77950-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="77950-139">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="77950-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
