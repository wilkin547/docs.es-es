---
title: Elemento &lt;windows&gt; de &lt;clientCredentials&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6687f93be26dedcb34f08770708c072742fdd4de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="5f774-102">Elemento &lt;windows&gt; de &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="5f774-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="5f774-103">Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5f774-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="5f774-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5f774-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f774-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5f774-105">\<behaviors></span></span>  
<span data-ttu-id="5f774-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5f774-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5f774-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5f774-107">\<behavior></span></span>  
<span data-ttu-id="5f774-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="5f774-108">\<clientCredentials></span></span>  
<span data-ttu-id="5f774-109">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="5f774-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f774-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f774-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f774-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f774-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5f774-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f774-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f774-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f774-113">Attributes</span></span>  
  
|<span data-ttu-id="5f774-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5f774-114">Attribute</span></span>|<span data-ttu-id="5f774-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f774-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="5f774-116">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="5f774-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="5f774-117">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5f774-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="5f774-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f774-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5f774-119">-Identificación: El servidor puede obtener la identidad y privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5f774-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="5f774-120">-Suplantación: El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="5f774-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="5f774-121">-Delegation: El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="5f774-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="5f774-122">-Anónima: El servidor no se puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5f774-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="5f774-123">-Ninguno: Un nivel de suplantación no está asignado.</span><span class="sxs-lookup"><span data-stu-id="5f774-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="5f774-124">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="5f774-124">The default is Identification.</span></span> <span data-ttu-id="5f774-125">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="5f774-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="5f774-126">Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="5f774-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="5f774-127">Establecer esta propiedad en `false` hace que [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] realice un mayor esfuerzo por iniciar una excepción si se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="5f774-127">Setting this property to `false` causes [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="5f774-128">Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="5f774-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f774-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f774-129">Child Elements</span></span>  
 <span data-ttu-id="5f774-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f774-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f774-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f774-131">Parent Elements</span></span>  
  
|<span data-ttu-id="5f774-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f774-132">Element</span></span>|<span data-ttu-id="5f774-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f774-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f774-134">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="5f774-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="5f774-135">Especifica las credenciales utilizadas para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="5f774-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f774-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f774-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="5f774-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="5f774-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="5f774-138">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5f774-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="5f774-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5f774-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
