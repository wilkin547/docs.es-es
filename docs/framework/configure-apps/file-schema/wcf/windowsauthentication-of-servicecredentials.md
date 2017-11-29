---
title: Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dbc4c3413213aa36468fde6e84671de0e0a31c2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="75ac6-102">Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="75ac6-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="75ac6-103">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="75ac6-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="75ac6-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="75ac6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="75ac6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="75ac6-105">\<behaviors></span></span>  
<span data-ttu-id="75ac6-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="75ac6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="75ac6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="75ac6-107">\<behavior></span></span>  
<span data-ttu-id="75ac6-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="75ac6-108">\<serviceCredentials></span></span>  
<span data-ttu-id="75ac6-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="75ac6-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ac6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75ac6-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75ac6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75ac6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="75ac6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75ac6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75ac6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="75ac6-113">Attributes</span></span>  
  
|<span data-ttu-id="75ac6-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="75ac6-114">Attribute</span></span>|<span data-ttu-id="75ac6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="75ac6-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="75ac6-116">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75ac6-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="75ac6-117">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="75ac6-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="75ac6-118">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="75ac6-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="75ac6-119">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="75ac6-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="75ac6-120">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="75ac6-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="75ac6-121">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="75ac6-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="75ac6-122">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="75ac6-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="75ac6-123">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="75ac6-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="75ac6-124">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="75ac6-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="75ac6-125">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="75ac6-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75ac6-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75ac6-126">Child Elements</span></span>  
 <span data-ttu-id="75ac6-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75ac6-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75ac6-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75ac6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="75ac6-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="75ac6-129">Element</span></span>|<span data-ttu-id="75ac6-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="75ac6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75ac6-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="75ac6-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="75ac6-132">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="75ac6-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75ac6-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75ac6-133">Remarks</span></span>  
 <span data-ttu-id="75ac6-134">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="75ac6-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="75ac6-135">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="75ac6-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="75ac6-136">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="75ac6-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ac6-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="75ac6-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
