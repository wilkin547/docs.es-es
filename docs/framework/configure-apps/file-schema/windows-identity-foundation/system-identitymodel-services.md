---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 9728f3caee4dba367e4fc4a3e68213b1055cc3d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793788"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="eb722-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="eb722-102">\<system.identityModel.services></span></span>
<span data-ttu-id="eb722-103">Sección de configuración para la autenticación mediante el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="eb722-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="eb722-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="eb722-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb722-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb722-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb722-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eb722-106">Attributes and Elements</span></span>  
 <span data-ttu-id="eb722-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eb722-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb722-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb722-108">Attributes</span></span>  
 <span data-ttu-id="eb722-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="eb722-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb722-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb722-110">Child Elements</span></span>  
  
|<span data-ttu-id="eb722-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb722-111">Element</span></span>|<span data-ttu-id="eb722-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb722-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb722-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="eb722-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="eb722-114">Contiene la configuración que establece el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> módulos HTTP (SAM).</span><span class="sxs-lookup"><span data-stu-id="eb722-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb722-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eb722-115">Parent Elements</span></span>  
 <span data-ttu-id="eb722-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="eb722-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb722-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb722-117">Remarks</span></span>  
 <span data-ttu-id="eb722-118">Agregar un `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración de SAM y WSFAM.</span><span class="sxs-lookup"><span data-stu-id="eb722-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb722-119">Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar control de acceso basado en notificaciones en el código, el Administrador de autorización de notificaciones (<xref:System.Security.Claims.ClaimsAuthorizationManager>) y la directiva que se usa para tomar decisiones de autorización se configuran a través de un `<identityConfiguration>` elemento al que hace referencia implícita o explícitamente desde un `<federationConfiguration>` elemento en esta sección.</span><span class="sxs-lookup"><span data-stu-id="eb722-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="eb722-120">Para obtener más información, consulte el **comentarios** bajo el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="eb722-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="eb722-121">El `<system.identityModel.services>` sección representada por la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase.</span><span class="sxs-lookup"><span data-stu-id="eb722-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="eb722-122">La colección del elemento secundario `<federationConfiguration>` configurados en la sección de elementos está representado por la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="eb722-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb722-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb722-123">Example</span></span>  
 <span data-ttu-id="eb722-124">El siguiente XML muestra cómo agregar un `<system.identityModel.services>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb722-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="eb722-125">En primer lugar debe agregar las declaraciones de sección tanto para el `<system.identityModel.services>` sección y la `<system.identityModel>` secciones.</span><span class="sxs-lookup"><span data-stu-id="eb722-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="eb722-126">(Cuando se agrega un `<system.identityModel.services>` sección, también debe agregar una declaración para el `<system.identityModel>` sección para asegurarse de que un valor predeterminado `<identityConfiguration>` sección puede crearse mediante el tiempo de ejecución si es necesario.) Después de han agregado las declaraciones de sección, puede configurar opciones de autenticación federada en el `<system.identityModel.services>` elemento.</span><span class="sxs-lookup"><span data-stu-id="eb722-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
