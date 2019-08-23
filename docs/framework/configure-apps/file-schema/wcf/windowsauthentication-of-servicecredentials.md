---
title: <windowsAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 81793b0d58a95166bc23f98d46ce94a5f1e1d018
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940289"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="1630a-102">\<> windowsAuthentication de \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1630a-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="1630a-103">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="1630a-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="1630a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1630a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1630a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1630a-105">\<behaviors></span></span>  
<span data-ttu-id="1630a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1630a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1630a-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1630a-107">\<behavior></span></span>  
<span data-ttu-id="1630a-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1630a-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1630a-109">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="1630a-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1630a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1630a-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1630a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1630a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1630a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1630a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1630a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="1630a-113">Attributes</span></span>  
  
|<span data-ttu-id="1630a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="1630a-114">Attribute</span></span>|<span data-ttu-id="1630a-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1630a-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="1630a-116">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1630a-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="1630a-117">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="1630a-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="1630a-118">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="1630a-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="1630a-119">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="1630a-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="1630a-120">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="1630a-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="1630a-121">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="1630a-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1630a-122">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="1630a-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="1630a-123">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="1630a-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="1630a-124">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="1630a-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="1630a-125">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="1630a-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1630a-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1630a-126">Child Elements</span></span>  
 <span data-ttu-id="1630a-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1630a-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1630a-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1630a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1630a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1630a-129">Element</span></span>|<span data-ttu-id="1630a-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1630a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1630a-131">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1630a-131">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="1630a-132">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="1630a-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1630a-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1630a-133">Remarks</span></span>  
 <span data-ttu-id="1630a-134">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="1630a-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="1630a-135">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="1630a-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="1630a-136">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="1630a-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1630a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1630a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
