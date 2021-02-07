---
description: 'Más información sobre: <windowsAuthentication> de <serviceCredentials>'
title: <windowsAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 94f5804ac22a8c3ee1b8fc646ece8521ff639aec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682415"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="23c65-103">\<windowsAuthentication> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="23c65-103">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="23c65-104">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="23c65-104">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="23c65-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23c65-105">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23c65-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="23c65-106">Attributes and Elements</span></span>  

 <span data-ttu-id="23c65-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="23c65-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23c65-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="23c65-108">Attributes</span></span>  
  
|<span data-ttu-id="23c65-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="23c65-109">Attribute</span></span>|<span data-ttu-id="23c65-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="23c65-110">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="23c65-111">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="23c65-111">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="23c65-112">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="23c65-112">The default is `true`.</span></span><br /><br /> <span data-ttu-id="23c65-113">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="23c65-113">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="23c65-114">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="23c65-114">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="23c65-115">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="23c65-115">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="23c65-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="23c65-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="23c65-117">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="23c65-117">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="23c65-118">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="23c65-118">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="23c65-119">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="23c65-119">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="23c65-120">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="23c65-120">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23c65-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="23c65-121">Child Elements</span></span>  

 <span data-ttu-id="23c65-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="23c65-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23c65-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="23c65-123">Parent Elements</span></span>  
  
|<span data-ttu-id="23c65-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="23c65-124">Element</span></span>|<span data-ttu-id="23c65-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="23c65-125">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="23c65-126">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="23c65-126">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c65-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23c65-127">Remarks</span></span>  

 <span data-ttu-id="23c65-128">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="23c65-128">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="23c65-129">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="23c65-129">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="23c65-130">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="23c65-130">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c65-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c65-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
