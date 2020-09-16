---
title: <httpDigest> (Elemento)
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 0ffaba218d31a77407c598f8b7fa0260daa4e39c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556907"
---
# <a name="httpdigest-element"></a><span data-ttu-id="e4cc8-102">\<httpDigest> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="e4cc8-102">\<httpDigest> Element</span></span>
<span data-ttu-id="e4cc8-103">Especifica una credencial de tipo de resumen utilizada al autenticar el cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="e4cc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4cc8-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4cc8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4cc8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e4cc8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4cc8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4cc8-107">Attributes</span></span>  
  
|<span data-ttu-id="e4cc8-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4cc8-108">Attribute</span></span>|<span data-ttu-id="e4cc8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4cc8-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="e4cc8-110">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="e4cc8-111">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="e4cc8-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4cc8-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4cc8-113">-Identification: el servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="e4cc8-114">-Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="e4cc8-115">-Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="e4cc8-116">-Anonymous: el servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="e4cc8-117">-None: no se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="e4cc8-118">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-118">The default is Identification.</span></span> <span data-ttu-id="e4cc8-119">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4cc8-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4cc8-120">Child Elements</span></span>  
 <span data-ttu-id="e4cc8-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4cc8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4cc8-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4cc8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e4cc8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4cc8-123">Element</span></span>|<span data-ttu-id="e4cc8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4cc8-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="e4cc8-125">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4cc8-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4cc8-126">Remarks</span></span>  
 <span data-ttu-id="e4cc8-127">Un resumen es un hash determinado mediante un algoritmo y un conjunto de entradas.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="e4cc8-128">El autenticador y los autenticados están de acuerdo en un algoritmo e intercambian los datos utilizados como entradas.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="e4cc8-129">El cliente puede calcular el hash y enviarlo al servicio.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="e4cc8-130">El servicio también calcula el hash y compara los valores.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="e4cc8-131">La coincidencia valida al cliente.</span><span class="sxs-lookup"><span data-stu-id="e4cc8-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="e4cc8-132">Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e4cc8-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="e4cc8-133">Para obtener más información, vea [autenticación implícita en IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="e4cc8-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cc8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4cc8-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="e4cc8-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e4cc8-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e4cc8-136">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="e4cc8-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="e4cc8-137">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="e4cc8-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e4cc8-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e4cc8-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
