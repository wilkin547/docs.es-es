---
title: <windowsAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195004"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="ec6bb-102">\<windowsAuthentication> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ec6bb-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="ec6bb-103">Especifica los valores de una credencial del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="ec6bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec6bb-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6bb-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ec6bb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ec6bb-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6bb-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec6bb-107">Attributes</span></span>  
  
|<span data-ttu-id="ec6bb-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ec6bb-108">Attribute</span></span>|<span data-ttu-id="ec6bb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec6bb-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="ec6bb-110">Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="ec6bb-111">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="ec6bb-112">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="ec6bb-113">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="ec6bb-114">Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="ec6bb-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="ec6bb-116">Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="ec6bb-117">Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="ec6bb-118">Se puede reemplazar este comportamiento utilizando este atributo.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="ec6bb-119">Utilice esta configuración con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec6bb-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec6bb-120">Child Elements</span></span>  

 <span data-ttu-id="ec6bb-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6bb-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ec6bb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6bb-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec6bb-123">Element</span></span>|<span data-ttu-id="ec6bb-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec6bb-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="ec6bb-125">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6bb-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec6bb-126">Remarks</span></span>  

 <span data-ttu-id="ec6bb-127">Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="ec6bb-128">También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="ec6bb-129">Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6bb-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6bb-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec6bb-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
