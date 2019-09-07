---
title: <windows>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399129"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="5ff1a-102">\<Windows > de \<elemento > clientCredentials</span><span class="sxs-lookup"><span data-stu-id="5ff1a-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="5ff1a-103">Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="5ff1a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5ff1a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5ff1a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5ff1a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5ff1a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5ff1a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5ff1a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="5ff1a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de Windows**</span><span class="sxs-lookup"><span data-stu-id="5ff1a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff1a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ff1a-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ff1a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ff1a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5ff1a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ff1a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ff1a-114">Attributes</span></span>  
  
|<span data-ttu-id="5ff1a-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ff1a-115">Attribute</span></span>|<span data-ttu-id="5ff1a-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff1a-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="5ff1a-117">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="5ff1a-118">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="5ff1a-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ff1a-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ff1a-120">Identificado El servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="5ff1a-121">Suplantación El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="5ff1a-122">Delegado El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="5ff1a-123">Anonymous El servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="5ff1a-124">Ninguna No se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="5ff1a-125">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-125">The default is Identification.</span></span> <span data-ttu-id="5ff1a-126">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="5ff1a-127">Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="5ff1a-128">Establecer esta propiedad en `false` hace que Windows Communication Foundation (WCF) realice un mejor esfuerzo para producir una excepción si se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="5ff1a-129">Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ff1a-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ff1a-130">Child Elements</span></span>  
 <span data-ttu-id="5ff1a-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ff1a-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ff1a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="5ff1a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ff1a-133">Element</span></span>|<span data-ttu-id="5ff1a-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff1a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ff1a-135">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5ff1a-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="5ff1a-136">Especifica las credenciales utilizadas para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ff1a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff1a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="5ff1a-138">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="5ff1a-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5ff1a-139">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5ff1a-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5ff1a-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5ff1a-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
