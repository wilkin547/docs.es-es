---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252078"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="52781-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="52781-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="52781-102">Registra un administrador de autorización de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="52781-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
<span data-ttu-id="52781-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52781-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52781-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="52781-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="52781-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="52781-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="52781-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimsAuthorizationManager**</span><span class="sxs-lookup"><span data-stu-id="52781-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52781-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52781-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52781-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="52781-108">Attributes and Elements</span></span>  
 <span data-ttu-id="52781-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="52781-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52781-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="52781-110">Attributes</span></span>  
  
|<span data-ttu-id="52781-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="52781-111">Attribute</span></span>|<span data-ttu-id="52781-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="52781-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52781-113">type</span><span class="sxs-lookup"><span data-stu-id="52781-113">type</span></span>|<span data-ttu-id="52781-114">Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="52781-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="52781-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="52781-115">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52781-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="52781-116">Child Elements</span></span>  
 <span data-ttu-id="52781-117">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia <xref:System.Security.Claims.ClaimsAuthenticationManager> a la clase `<claimsAuthorizationManager>` , el elemento no toma los elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthorizationManager> las clases derivadas de pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="52781-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52781-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="52781-118">Parent Elements</span></span>  
  
|<span data-ttu-id="52781-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="52781-119">Element</span></span>|<span data-ttu-id="52781-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="52781-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52781-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="52781-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="52781-122">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="52781-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52781-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52781-123">Remarks</span></span>  
 <span data-ttu-id="52781-124">El comportamiento predeterminado proporcionado a través <xref:System.Security.Claims.ClaimsAuthorizationManager> de la clase siempre autoriza las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="52781-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="52781-125">Si no `type` se especifica ningún atributo o si `type` el atributo especifica <xref:System.Security.Claims.ClaimsAuthorizationManager> la clase, `<claimsAuthorizationManager>` el elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="52781-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="52781-126">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="52781-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="52781-127">Las clases derivadas pueden admitir la configuración a través `<claimsAuthorizationManager>` de elementos secundarios del elemento <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> invalidando el método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="52781-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="52781-128">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="52781-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="52781-129">Cuando se usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que `<federationConfiguration>` hace referencia el elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para realizar decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="52781-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="52781-130">Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web.</span><span class="sxs-lookup"><span data-stu-id="52781-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="52781-131">Si la aplicación no es una aplicación web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados.</span><span class="sxs-lookup"><span data-stu-id="52781-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="52781-132">Se omiten todas las demás configuraciones.</span><span class="sxs-lookup"><span data-stu-id="52781-132">All other settings are ignored.</span></span> <span data-ttu-id="52781-133">Para obtener más información, vea [ \<](federationconfiguration.md) el elemento > de federationConfiguration.</span><span class="sxs-lookup"><span data-stu-id="52781-133">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="52781-134">Este elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="52781-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52781-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52781-135">Example</span></span>  
 <span data-ttu-id="52781-136">En el XML siguiente se muestra la configuración de un administrador de autorización de notificaciones que implementa la Directiva formada por pares de acción-recurso, cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso.</span><span class="sxs-lookup"><span data-stu-id="52781-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="52781-137">El código que implementa el administrador de autorización de notificaciones capaz de usar esta Directiva se puede encontrar `ClaimsBasedAuthorization` en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="52781-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
