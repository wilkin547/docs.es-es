---
description: 'Más información acerca de: <claimsAuthorizationManager>'
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ae96c9e665c8533567ad87cad374919c30a6b3c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664241"
---
# \<claimsAuthorizationManager>

<span data-ttu-id="ca1b4-102">Registra un administrador de autorización de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="ca1b4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca1b4-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca1b4-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca1b4-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ca1b4-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca1b4-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca1b4-106">Attributes</span></span>  
  
|<span data-ttu-id="ca1b4-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ca1b4-107">Attribute</span></span>|<span data-ttu-id="ca1b4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca1b4-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca1b4-109">type</span><span class="sxs-lookup"><span data-stu-id="ca1b4-109">type</span></span>|<span data-ttu-id="ca1b4-110">Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-110">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="ca1b4-111">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca1b4-111">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca1b4-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca1b4-112">Child Elements</span></span>  

 <span data-ttu-id="ca1b4-113">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-113">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca1b4-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca1b4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ca1b4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca1b4-115">Element</span></span>|<span data-ttu-id="ca1b4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca1b4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="ca1b4-117">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-117">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca1b4-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca1b4-118">Remarks</span></span>  

 <span data-ttu-id="ca1b4-119">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-119">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="ca1b4-120">Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-120">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="ca1b4-121">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-121">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="ca1b4-122">Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthorizationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-122">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="ca1b4-123">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-123">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca1b4-124">Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que hace referencia el `<federationConfiguration>` elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para tomar decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-124">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="ca1b4-125">Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-125">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="ca1b4-126">Si la aplicación no es una aplicación web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-126">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="ca1b4-127">Todos los demás valores no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-127">All other settings are ignored.</span></span> <span data-ttu-id="ca1b4-128">Para obtener más información, vea el [\<federationConfiguration>](federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-128">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="ca1b4-129">Este elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-129">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1b4-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca1b4-130">Example</span></span>  

 <span data-ttu-id="ca1b4-131">En el XML siguiente se muestra la configuración de un administrador de autorización de notificaciones que implementa la Directiva formada por pares de acción-recurso, cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-131">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="ca1b4-132">El código que implementa el administrador de autorización de notificaciones capaz de usar esta Directiva se puede encontrar en el `ClaimsBasedAuthorization` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca1b4-132">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
