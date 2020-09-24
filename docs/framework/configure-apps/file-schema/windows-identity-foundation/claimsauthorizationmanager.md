---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 0718f789ff4d99fb4e2651a9a704da4248cd5f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158440"
---
# \<claimsAuthorizationManager>

<span data-ttu-id="d412f-101">Registra un administrador de autorización de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="d412f-101">Registers a claims authorization manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="d412f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d412f-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d412f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d412f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d412f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d412f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d412f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d412f-105">Attributes</span></span>  
  
|<span data-ttu-id="d412f-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d412f-106">Attribute</span></span>|<span data-ttu-id="d412f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d412f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d412f-108">type</span><span class="sxs-lookup"><span data-stu-id="d412f-108">type</span></span>|<span data-ttu-id="d412f-109">Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="d412f-109">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="d412f-110">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d412f-110">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d412f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d412f-111">Child Elements</span></span>  

 <span data-ttu-id="d412f-112">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="d412f-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d412f-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d412f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d412f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d412f-114">Element</span></span>|<span data-ttu-id="d412f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d412f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="d412f-116">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="d412f-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d412f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d412f-117">Remarks</span></span>  

 <span data-ttu-id="d412f-118">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="d412f-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="d412f-119">Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d412f-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="d412f-120">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="d412f-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="d412f-121">Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthorizationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="d412f-121">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="d412f-122">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="d412f-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d412f-123">Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que hace referencia el `<federationConfiguration>` elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para tomar decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="d412f-123">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="d412f-124">Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web.</span><span class="sxs-lookup"><span data-stu-id="d412f-124">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="d412f-125">Si la aplicación no es una aplicación web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados.</span><span class="sxs-lookup"><span data-stu-id="d412f-125">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="d412f-126">Todos los demás valores no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d412f-126">All other settings are ignored.</span></span> <span data-ttu-id="d412f-127">Para obtener más información, vea el [\<federationConfiguration>](federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d412f-127">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="d412f-128">Este elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d412f-128">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d412f-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d412f-129">Example</span></span>  

 <span data-ttu-id="d412f-130">En el XML siguiente se muestra la configuración de un administrador de autorización de notificaciones que implementa la Directiva formada por pares de acción-recurso, cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso.</span><span class="sxs-lookup"><span data-stu-id="d412f-130">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="d412f-131">El código que implementa el administrador de autorización de notificaciones capaz de usar esta Directiva se puede encontrar en el `ClaimsBasedAuthorization` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d412f-131">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
