---
title: <httpDigest> (Elemento)
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397990"
---
# <a name="httpdigest-element"></a><span data-ttu-id="29e10-102">\<httpDigest >, elemento</span><span class="sxs-lookup"><span data-stu-id="29e10-102">\<httpDigest> Element</span></span>
<span data-ttu-id="29e10-103">Especifica una credencial de tipo de resumen utilizada al autenticar el cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="29e10-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="29e10-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="29e10-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="29e10-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="29e10-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="29e10-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="29e10-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="29e10-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="29e10-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> httpDigest**</span><span class="sxs-lookup"><span data-stu-id="29e10-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e10-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29e10-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29e10-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29e10-112">Attributes and Elements</span></span>  
 <span data-ttu-id="29e10-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29e10-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29e10-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="29e10-114">Attributes</span></span>  
  
|<span data-ttu-id="29e10-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="29e10-115">Attribute</span></span>|<span data-ttu-id="29e10-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29e10-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="29e10-117">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="29e10-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="29e10-118">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="29e10-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="29e10-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="29e10-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29e10-120">Identificado El servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="29e10-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="29e10-121">Suplantación El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="29e10-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="29e10-122">Delegado El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="29e10-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="29e10-123">Anonymous El servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="29e10-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="29e10-124">Ninguna No se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="29e10-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="29e10-125">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="29e10-125">The default is Identification.</span></span> <span data-ttu-id="29e10-126">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="29e10-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29e10-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29e10-127">Child Elements</span></span>  
 <span data-ttu-id="29e10-128">None</span><span class="sxs-lookup"><span data-stu-id="29e10-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29e10-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29e10-129">Parent Elements</span></span>  
  
|<span data-ttu-id="29e10-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="29e10-130">Element</span></span>|<span data-ttu-id="29e10-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29e10-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29e10-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="29e10-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="29e10-133">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="29e10-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e10-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29e10-134">Remarks</span></span>  
 <span data-ttu-id="29e10-135">Un resumen es un hash determinado mediante un algoritmo y un conjunto de entradas.</span><span class="sxs-lookup"><span data-stu-id="29e10-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="29e10-136">El autenticador y los autenticados están de acuerdo en un algoritmo e intercambian los datos utilizados como entradas.</span><span class="sxs-lookup"><span data-stu-id="29e10-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="29e10-137">El cliente puede calcular el hash y enviarlo al servicio.</span><span class="sxs-lookup"><span data-stu-id="29e10-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="29e10-138">El servicio también calcula el hash y compara los valores.</span><span class="sxs-lookup"><span data-stu-id="29e10-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="29e10-139">La coincidencia valida al cliente.</span><span class="sxs-lookup"><span data-stu-id="29e10-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="29e10-140">Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="29e10-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="29e10-141">Para obtener más información, vea [autenticación implícita en IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="29e10-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e10-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="29e10-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="29e10-143">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="29e10-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="29e10-144">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="29e10-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="29e10-145">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="29e10-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="29e10-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="29e10-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
