---
title: <windows> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 115e1822659c04ee37a7364f7b25616b52dc5efe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177831"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="c5213-102">\<windows> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="c5213-102">\<windows> of \<clientCredentials> Element</span></span>

<span data-ttu-id="c5213-103">Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.</span><span class="sxs-lookup"><span data-stu-id="c5213-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="c5213-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5213-104">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5213-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c5213-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c5213-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c5213-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5213-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c5213-107">Attributes</span></span>  
  
|<span data-ttu-id="c5213-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c5213-108">Attribute</span></span>|<span data-ttu-id="c5213-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5213-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="c5213-110">Establece la preferencia de suplantación que el cliente comunica al servidor.</span><span class="sxs-lookup"><span data-stu-id="c5213-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="c5213-111">El modo de suplantación que el cliente elige no se exige en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c5213-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="c5213-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5213-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c5213-113">-Identification: el servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.</span><span class="sxs-lookup"><span data-stu-id="c5213-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="c5213-114">-Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="c5213-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="c5213-115">-Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="c5213-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="c5213-116">-Anonymous: el servidor no puede suplantar o identificar al cliente.</span><span class="sxs-lookup"><span data-stu-id="c5213-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="c5213-117">-None: no se ha asignado un nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="c5213-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="c5213-118">El valor predeterminado es Identification.</span><span class="sxs-lookup"><span data-stu-id="c5213-118">The default is Identification.</span></span> <span data-ttu-id="c5213-119">Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="c5213-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="c5213-120">Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c5213-120">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="c5213-121">Establecer esta propiedad en `false` hace que Windows Communication Foundation (WCF) realice un mejor esfuerzo para producir una excepción si se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="c5213-121">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="c5213-122">Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="c5213-122">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5213-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c5213-123">Child Elements</span></span>  

 <span data-ttu-id="c5213-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c5213-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5213-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c5213-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c5213-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5213-126">Element</span></span>|<span data-ttu-id="c5213-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5213-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="c5213-128">Especifica las credenciales utilizadas para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="c5213-128">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5213-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5213-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="c5213-130">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="c5213-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c5213-131">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c5213-131">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c5213-132">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c5213-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
