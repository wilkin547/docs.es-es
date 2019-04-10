---
title: <windows> de <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: b5e92745b9e39534d2a0bc35504c2dbc8346d2ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221025"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="d7dd9-102">\<Windows > de \<clientCredentials > elemento</span><span class="sxs-lookup"><span data-stu-id="d7dd9-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="d7dd9-103">Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="d7dd9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d7dd9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7dd9-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d7dd9-105">\<behaviors></span></span>  
<span data-ttu-id="d7dd9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d7dd9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d7dd9-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d7dd9-107">\<behavior></span></span>  
<span data-ttu-id="d7dd9-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d7dd9-108">\<clientCredentials></span></span>  
<span data-ttu-id="d7dd9-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="d7dd9-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7dd9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7dd9-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7dd9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d7dd9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d7dd9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7dd9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7dd9-113">Attributes</span></span>  
  
|<span data-ttu-id="d7dd9-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d7dd9-114">Attribute</span></span>|<span data-ttu-id="d7dd9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7dd9-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="d7dd9-116">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="d7dd9-117">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="d7dd9-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7dd9-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d7dd9-119">-Identificación: El servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="d7dd9-120">-Suplantación: El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="d7dd9-121">-Delegación: El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="d7dd9-122">-Anónimo: El servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="d7dd9-123">-None: No se asigna un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="d7dd9-124">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-124">The default is Identification.</span></span> <span data-ttu-id="d7dd9-125">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="d7dd9-126">Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="d7dd9-127">Establecer esta propiedad en `false` hace que Windows Communication Foundation (WCF) para realizar un mayor esfuerzo para producir una excepción si se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="d7dd9-128">Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7dd9-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d7dd9-129">Child Elements</span></span>  
 <span data-ttu-id="d7dd9-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7dd9-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d7dd9-131">Parent Elements</span></span>  
  
|<span data-ttu-id="d7dd9-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7dd9-132">Element</span></span>|<span data-ttu-id="d7dd9-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7dd9-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7dd9-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d7dd9-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="d7dd9-135">Especifica las credenciales utilizadas para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="d7dd9-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7dd9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7dd9-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="d7dd9-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d7dd9-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="d7dd9-138">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="d7dd9-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d7dd9-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d7dd9-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
