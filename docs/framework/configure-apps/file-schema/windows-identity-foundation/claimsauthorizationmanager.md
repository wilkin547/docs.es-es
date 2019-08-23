---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 74ca031f7017d51adaa7a71593f537b64abbeae6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942893"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="71e4b-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="71e4b-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="71e4b-102">Registra un administrador de autorización de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="71e4b-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="71e4b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="71e4b-103">\<system.identityModel></span></span>  
<span data-ttu-id="71e4b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="71e4b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="71e4b-105">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="71e4b-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e4b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71e4b-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71e4b-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71e4b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="71e4b-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71e4b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71e4b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="71e4b-109">Attributes</span></span>  
  
|<span data-ttu-id="71e4b-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="71e4b-110">Attribute</span></span>|<span data-ttu-id="71e4b-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="71e4b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71e4b-112">type</span><span class="sxs-lookup"><span data-stu-id="71e4b-112">type</span></span>|<span data-ttu-id="71e4b-113">Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="71e4b-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="71e4b-114">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="71e4b-114">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71e4b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71e4b-115">Child Elements</span></span>  
 <span data-ttu-id="71e4b-116">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia <xref:System.Security.Claims.ClaimsAuthenticationManager> a la clase `<claimsAuthorizationManager>` , el elemento no toma los elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthorizationManager> las clases derivadas de pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="71e4b-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71e4b-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71e4b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="71e4b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="71e4b-118">Element</span></span>|<span data-ttu-id="71e4b-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="71e4b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71e4b-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="71e4b-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="71e4b-121">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="71e4b-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71e4b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71e4b-122">Remarks</span></span>  
 <span data-ttu-id="71e4b-123">El comportamiento predeterminado proporcionado a través <xref:System.Security.Claims.ClaimsAuthorizationManager> de la clase siempre autoriza las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="71e4b-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="71e4b-124">Si no `type` se especifica ningún atributo o si `type` el atributo especifica <xref:System.Security.Claims.ClaimsAuthorizationManager> la clase, `<claimsAuthorizationManager>` el elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="71e4b-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="71e4b-125">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="71e4b-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="71e4b-126">Las clases derivadas pueden admitir la configuración a través `<claimsAuthorizationManager>` de elementos secundarios del elemento <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> invalidando el método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="71e4b-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="71e4b-127">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="71e4b-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="71e4b-128">Cuando se usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que `<federationConfiguration>` hace referencia el elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para realizar decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="71e4b-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="71e4b-129">Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web.</span><span class="sxs-lookup"><span data-stu-id="71e4b-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="71e4b-130">Si la aplicación no es una aplicación web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados.</span><span class="sxs-lookup"><span data-stu-id="71e4b-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="71e4b-131">Se omiten todas las demás configuraciones.</span><span class="sxs-lookup"><span data-stu-id="71e4b-131">All other settings are ignored.</span></span> <span data-ttu-id="71e4b-132">Para obtener más información, vea [ \<](federationconfiguration.md) el elemento > de federationConfiguration.</span><span class="sxs-lookup"><span data-stu-id="71e4b-132">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="71e4b-133">Este elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="71e4b-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71e4b-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71e4b-134">Example</span></span>  
 <span data-ttu-id="71e4b-135">En el XML siguiente se muestra la configuración de un administrador de autorización de notificaciones que implementa la Directiva formada por pares de acción-recurso, cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso.</span><span class="sxs-lookup"><span data-stu-id="71e4b-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="71e4b-136">El código que implementa el administrador de autorización de notificaciones capaz de usar esta Directiva se puede encontrar `ClaimsBasedAuthorization` en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="71e4b-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
