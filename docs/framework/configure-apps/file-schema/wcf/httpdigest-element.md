---
title: <httpDigest> (Elemento)
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: c930efbc2cd7a6dc12795d5ac1c26ea92fc36599
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259012"
---
# <a name="httpdigest-element"></a><span data-ttu-id="a0994-102">\<httpDigest > elemento</span><span class="sxs-lookup"><span data-stu-id="a0994-102">\<httpDigest> Element</span></span>
<span data-ttu-id="a0994-103">Especifica una credencial de tipo de resumen utilizada al autenticar el cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="a0994-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="a0994-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0994-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0994-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a0994-105">\<behaviors></span></span>  
<span data-ttu-id="a0994-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a0994-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a0994-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a0994-107">\<behavior></span></span>  
<span data-ttu-id="a0994-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a0994-108">\<clientCredentials></span></span>  
<span data-ttu-id="a0994-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="a0994-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0994-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0994-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0994-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0994-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a0994-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0994-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0994-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0994-113">Attributes</span></span>  
  
|<span data-ttu-id="a0994-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0994-114">Attribute</span></span>|<span data-ttu-id="a0994-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0994-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="a0994-116">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="a0994-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="a0994-117">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a0994-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="a0994-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0994-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a0994-119">-Identificación: El servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="a0994-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="a0994-120">-Suplantación: El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="a0994-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="a0994-121">-Delegación: El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="a0994-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="a0994-122">-Anónimo: El servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="a0994-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="a0994-123">-None: No se asigna un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="a0994-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="a0994-124">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="a0994-124">The default is Identification.</span></span> <span data-ttu-id="a0994-125">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="a0994-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0994-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0994-126">Child Elements</span></span>  
 <span data-ttu-id="a0994-127">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a0994-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0994-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0994-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a0994-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0994-129">Element</span></span>|<span data-ttu-id="a0994-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0994-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0994-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a0994-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="a0994-132">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="a0994-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0994-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0994-133">Remarks</span></span>  
 <span data-ttu-id="a0994-134">Un resumen es un hash determinado mediante un algoritmo y un conjunto de entradas.</span><span class="sxs-lookup"><span data-stu-id="a0994-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="a0994-135">El autenticador y los autenticados están de acuerdo en un algoritmo e intercambian los datos utilizados como entradas.</span><span class="sxs-lookup"><span data-stu-id="a0994-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="a0994-136">El cliente puede calcular el hash y enviarlo al servicio.</span><span class="sxs-lookup"><span data-stu-id="a0994-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="a0994-137">El servicio también calcula el hash y compara los valores.</span><span class="sxs-lookup"><span data-stu-id="a0994-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="a0994-138">La coincidencia valida al cliente.</span><span class="sxs-lookup"><span data-stu-id="a0994-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="a0994-139">Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a0994-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="a0994-140">Para obtener más información, consulte [la autenticación implícita en IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="a0994-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0994-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0994-141">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="a0994-142">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="a0994-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a0994-143">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="a0994-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="a0994-144">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="a0994-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a0994-145">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a0994-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
