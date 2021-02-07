---
description: 'Más información sobre: <windows> del <clientCredentials> elemento'
title: <windows> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: d693ad914dfa02ef12a7c8520ca84be3a9595e73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682428"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="effea-103">\<windows> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="effea-103">\<windows> of \<clientCredentials> Element</span></span>

<span data-ttu-id="effea-104">Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.</span><span class="sxs-lookup"><span data-stu-id="effea-104">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="effea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="effea-105">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="effea-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="effea-106">Attributes and Elements</span></span>  

 <span data-ttu-id="effea-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="effea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="effea-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="effea-108">Attributes</span></span>  
  
|<span data-ttu-id="effea-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="effea-109">Attribute</span></span>|<span data-ttu-id="effea-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="effea-110">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="effea-111">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="effea-111">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="effea-112">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="effea-112">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="effea-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="effea-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="effea-114">-Identification: el servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="effea-114">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="effea-115">-Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="effea-115">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="effea-116">-Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="effea-116">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="effea-117">-Anonymous: el servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="effea-117">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="effea-118">-None: no se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="effea-118">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="effea-119">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="effea-119">The default is Identification.</span></span> <span data-ttu-id="effea-120">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="effea-120">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="effea-121">Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="effea-121">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="effea-122">Establecer esta propiedad en `false` hace que Windows Communication Foundation (WCF) realice un mejor esfuerzo para producir una excepción si se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="effea-122">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="effea-123">Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="effea-123">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="effea-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="effea-124">Child Elements</span></span>  

 <span data-ttu-id="effea-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="effea-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="effea-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="effea-126">Parent Elements</span></span>  
  
|<span data-ttu-id="effea-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="effea-127">Element</span></span>|<span data-ttu-id="effea-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="effea-128">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="effea-129">Especifica las credenciales utilizadas para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="effea-129">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="effea-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="effea-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="effea-131">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="effea-131">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="effea-132">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="effea-132">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="effea-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="effea-133">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
