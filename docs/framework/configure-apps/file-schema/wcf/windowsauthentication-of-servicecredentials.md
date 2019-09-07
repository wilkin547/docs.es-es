---
title: <windowsAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399113"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="a112c-102">\<> windowsAuthentication de \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a112c-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="a112c-103">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="a112c-103">Specifies the settings of a Windows service credential.</span></span>  
  
<span data-ttu-id="a112c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a112c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a112c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a112c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a112c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a112c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="a112c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="a112c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> windowsAuthentication**</span><span class="sxs-lookup"><span data-stu-id="a112c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a112c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a112c-111">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a112c-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a112c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a112c-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a112c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a112c-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="a112c-114">Attributes</span></span>  
  
|<span data-ttu-id="a112c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="a112c-115">Attribute</span></span>|<span data-ttu-id="a112c-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a112c-116">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="a112c-117">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a112c-117">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="a112c-118">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a112c-118">The default is `true`.</span></span><br /><br /> <span data-ttu-id="a112c-119">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="a112c-119">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="a112c-120">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="a112c-120">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="a112c-121">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="a112c-121">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="a112c-122">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a112c-122">The default is `false`.</span></span><br /><br /> <span data-ttu-id="a112c-123">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="a112c-123">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="a112c-124">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="a112c-124">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="a112c-125">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="a112c-125">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="a112c-126">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="a112c-126">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a112c-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a112c-127">Child Elements</span></span>  
 <span data-ttu-id="a112c-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a112c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a112c-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a112c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a112c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a112c-130">Element</span></span>|<span data-ttu-id="a112c-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a112c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a112c-132">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a112c-132">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="a112c-133">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="a112c-133">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a112c-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a112c-134">Remarks</span></span>  
 <span data-ttu-id="a112c-135">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="a112c-135">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="a112c-136">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="a112c-136">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="a112c-137">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="a112c-137">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a112c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a112c-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
