---
title: <httpDigest> (Elemento)
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2ceefdd7fab82025e89ad08d8423d57524c2e4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925560"
---
# <a name="httpdigest-element"></a><span data-ttu-id="88ba6-102">\<httpDigest >, elemento</span><span class="sxs-lookup"><span data-stu-id="88ba6-102">\<httpDigest> Element</span></span>
<span data-ttu-id="88ba6-103">Especifica una credencial de tipo de resumen utilizada al autenticar el cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="88ba6-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="88ba6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="88ba6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="88ba6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="88ba6-105">\<behaviors></span></span>  
<span data-ttu-id="88ba6-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="88ba6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="88ba6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="88ba6-107">\<behavior></span></span>  
<span data-ttu-id="88ba6-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="88ba6-108">\<clientCredentials></span></span>  
<span data-ttu-id="88ba6-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="88ba6-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88ba6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88ba6-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88ba6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88ba6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="88ba6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88ba6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88ba6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="88ba6-113">Attributes</span></span>  
  
|<span data-ttu-id="88ba6-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="88ba6-114">Attribute</span></span>|<span data-ttu-id="88ba6-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="88ba6-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="88ba6-116">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="88ba6-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="88ba6-117">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="88ba6-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="88ba6-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="88ba6-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="88ba6-119">Identificado El servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="88ba6-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="88ba6-120">Suplantación El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="88ba6-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="88ba6-121">Delegado El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="88ba6-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="88ba6-122">Anonymous El servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="88ba6-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="88ba6-123">Ninguna No se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="88ba6-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="88ba6-124">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="88ba6-124">The default is Identification.</span></span> <span data-ttu-id="88ba6-125">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="88ba6-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88ba6-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88ba6-126">Child Elements</span></span>  
 <span data-ttu-id="88ba6-127">None</span><span class="sxs-lookup"><span data-stu-id="88ba6-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88ba6-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88ba6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="88ba6-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="88ba6-129">Element</span></span>|<span data-ttu-id="88ba6-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="88ba6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88ba6-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="88ba6-131">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="88ba6-132">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="88ba6-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88ba6-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88ba6-133">Remarks</span></span>  
 <span data-ttu-id="88ba6-134">Un resumen es un hash determinado mediante un algoritmo y un conjunto de entradas.</span><span class="sxs-lookup"><span data-stu-id="88ba6-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="88ba6-135">El autenticador y los autenticados están de acuerdo en un algoritmo e intercambian los datos utilizados como entradas.</span><span class="sxs-lookup"><span data-stu-id="88ba6-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="88ba6-136">El cliente puede calcular el hash y enviarlo al servicio.</span><span class="sxs-lookup"><span data-stu-id="88ba6-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="88ba6-137">El servicio también calcula el hash y compara los valores.</span><span class="sxs-lookup"><span data-stu-id="88ba6-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="88ba6-138">La coincidencia valida al cliente.</span><span class="sxs-lookup"><span data-stu-id="88ba6-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="88ba6-139">Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="88ba6-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="88ba6-140">Para obtener más información, vea [autenticación implícita en IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="88ba6-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ba6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="88ba6-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="88ba6-142">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="88ba6-142">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="88ba6-143">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="88ba6-143">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="88ba6-144">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="88ba6-144">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="88ba6-145">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="88ba6-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
