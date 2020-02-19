---
title: <httpDigest> (Elemento)
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 328411a429cd42927a190c6805a1f5e2b3555ea1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448457"
---
# <a name="httpdigest-element"></a><span data-ttu-id="9b7ce-102">\<elemento > httpDigest</span><span class="sxs-lookup"><span data-stu-id="9b7ce-102">\<httpDigest> Element</span></span>
<span data-ttu-id="9b7ce-103">Especifica una credencial de tipo de resumen utilizada al autenticar el cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="9b7ce-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b7ce-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b7ce-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b7ce-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9b7ce-106">&nbsp;&nbsp;&nbsp;&nbsp;[**comportamientos**](behaviors.md)\<></span><span class="sxs-lookup"><span data-stu-id="9b7ce-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9b7ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors**](endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="9b7ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="9b7ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**comportamiento**](behavior-of-endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="9b7ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="9b7ce-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**clientCredentials**](clientcredentials.md) ></span><span class="sxs-lookup"><span data-stu-id="9b7ce-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="9b7ce-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpDigest >**</span><span class="sxs-lookup"><span data-stu-id="9b7ce-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7ce-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b7ce-111">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b7ce-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b7ce-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9b7ce-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b7ce-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b7ce-114">Attributes</span></span>  
  
|<span data-ttu-id="9b7ce-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b7ce-115">Attribute</span></span>|<span data-ttu-id="9b7ce-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b7ce-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="9b7ce-117">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="9b7ce-118">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="9b7ce-119">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b7ce-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9b7ce-120">-Identification: el servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="9b7ce-121">-Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="9b7ce-122">-Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="9b7ce-123">-Anonymous: el servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="9b7ce-124">-None: no se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="9b7ce-125">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-125">The default is Identification.</span></span> <span data-ttu-id="9b7ce-126">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b7ce-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b7ce-127">Child Elements</span></span>  
 <span data-ttu-id="9b7ce-128">None</span><span class="sxs-lookup"><span data-stu-id="9b7ce-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b7ce-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b7ce-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9b7ce-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b7ce-130">Element</span></span>|<span data-ttu-id="9b7ce-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b7ce-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b7ce-132">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9b7ce-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="9b7ce-133">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b7ce-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b7ce-134">Remarks</span></span>  
 <span data-ttu-id="9b7ce-135">Un resumen es un hash determinado mediante un algoritmo y un conjunto de entradas.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="9b7ce-136">El autenticador y los autenticados están de acuerdo en un algoritmo e intercambian los datos utilizados como entradas.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="9b7ce-137">El cliente puede calcular el hash y enviarlo al servicio.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="9b7ce-138">El servicio también calcula el hash y compara los valores.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="9b7ce-139">La coincidencia valida al cliente.</span><span class="sxs-lookup"><span data-stu-id="9b7ce-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="9b7ce-140">Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="9b7ce-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="9b7ce-141">Para obtener más información, vea [autenticación implícita en IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="9b7ce-141">For more information, see [Digest Authentication in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7ce-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b7ce-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="9b7ce-143">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="9b7ce-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9b7ce-144">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="9b7ce-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="9b7ce-145">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="9b7ce-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9b7ce-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9b7ce-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
