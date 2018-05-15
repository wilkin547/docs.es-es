---
title: Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 9872b1f2520661ff3f31cef94b6822bb345ebfdf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="349a1-102">Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="349a1-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="349a1-103">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="349a1-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="349a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="349a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="349a1-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="349a1-105">\<behaviors></span></span>  
<span data-ttu-id="349a1-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="349a1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="349a1-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="349a1-107">\<behavior></span></span>  
<span data-ttu-id="349a1-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="349a1-108">\<serviceCredentials></span></span>  
<span data-ttu-id="349a1-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="349a1-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="349a1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="349a1-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="349a1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="349a1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="349a1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="349a1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="349a1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="349a1-113">Attributes</span></span>  
  
|<span data-ttu-id="349a1-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="349a1-114">Attribute</span></span>|<span data-ttu-id="349a1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="349a1-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="349a1-116">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="349a1-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="349a1-117">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="349a1-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="349a1-118">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="349a1-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="349a1-119">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="349a1-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="349a1-120">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="349a1-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="349a1-121">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="349a1-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="349a1-122">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="349a1-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="349a1-123">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="349a1-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="349a1-124">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="349a1-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="349a1-125">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="349a1-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="349a1-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="349a1-126">Child Elements</span></span>  
 <span data-ttu-id="349a1-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="349a1-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="349a1-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="349a1-128">Parent Elements</span></span>  
  
|<span data-ttu-id="349a1-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="349a1-129">Element</span></span>|<span data-ttu-id="349a1-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="349a1-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="349a1-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="349a1-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="349a1-132">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="349a1-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="349a1-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="349a1-133">Remarks</span></span>  
 <span data-ttu-id="349a1-134">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="349a1-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="349a1-135">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="349a1-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="349a1-136">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="349a1-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349a1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="349a1-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
