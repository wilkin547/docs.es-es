---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4b4d86204d5f7225f167be125ce017488c851e98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="2ea08-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="2ea08-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="2ea08-103">Registra un administrador de autorización de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="2ea08-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="2ea08-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="2ea08-104">\<system.identityModel></span></span>  
<span data-ttu-id="2ea08-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2ea08-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2ea08-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="2ea08-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea08-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ea08-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ea08-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2ea08-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2ea08-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2ea08-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ea08-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2ea08-110">Attributes</span></span>  
  
|<span data-ttu-id="2ea08-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2ea08-111">Attribute</span></span>|<span data-ttu-id="2ea08-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ea08-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ea08-113">type</span><span class="sxs-lookup"><span data-stu-id="2ea08-113">type</span></span>|<span data-ttu-id="2ea08-114">Un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="2ea08-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="2ea08-115">Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ea08-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ea08-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2ea08-116">Child Elements</span></span>  
 <span data-ttu-id="2ea08-117">Si no hay ningún `type` atributo, o si la `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> puede definir los elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="2ea08-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ea08-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2ea08-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2ea08-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ea08-119">Element</span></span>|<span data-ttu-id="2ea08-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ea08-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ea08-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2ea08-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="2ea08-122">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ea08-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ea08-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ea08-123">Remarks</span></span>  
 <span data-ttu-id="2ea08-124">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="2ea08-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="2ea08-125">Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthorizationManager> (clase), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="2ea08-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="2ea08-126">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ea08-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="2ea08-127">Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthorizationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="2ea08-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="2ea08-128">El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="2ea08-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ea08-129">Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar el control de acceso basado en notificaciones en el código, la configuración de identidad que hace referencia el `<federationConfiguration>` elemento configura el Administrador de autorización de notificaciones y la directiva que se utiliza para realizar decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="2ea08-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="2ea08-130">Esto es cierto incluso en escenarios que no son escenarios pasivos de Web, por ejemplo, las aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no esté basado en Web.</span><span class="sxs-lookup"><span data-stu-id="2ea08-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="2ea08-131">Si la aplicación no es una aplicación Web pasiva, el `<claimsAuthorizationManager>` element (y sus elementos de directiva secundarios, si está presente) de la configuración de identidad que se hace referencia son los únicos valores que se aplican.</span><span class="sxs-lookup"><span data-stu-id="2ea08-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="2ea08-132">Se omiten todas las demás opciones.</span><span class="sxs-lookup"><span data-stu-id="2ea08-132">All other settings are ignored.</span></span> <span data-ttu-id="2ea08-133">Para obtener más información, consulte el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2ea08-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="2ea08-134">Este elemento establece el <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2ea08-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ea08-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ea08-135">Example</span></span>  
 <span data-ttu-id="2ea08-136">El siguiente XML muestra la configuración de una autorización de notificaciones de administrador que implementa la directiva formada por pares de acción del recurso de cada uno de los cuales especifica booleanos combinaciones de las notificaciones que debe poseer un solicitante para realizar la acción en el recurso.</span><span class="sxs-lookup"><span data-stu-id="2ea08-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="2ea08-137">El código que implementa el Administrador de autorización de notificaciones capaz de usar esta directiva puede encontrarse en la `ClaimsBasedAuthorization` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2ea08-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
