---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152509"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="97d94-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="97d94-102">\<system.identityModel.services></span></span>
<span data-ttu-id="97d94-103">Sección de configuración para la autenticación mediante el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="97d94-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="97d94-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97d94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97d94-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span><span class="sxs-lookup"><span data-stu-id="97d94-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d94-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97d94-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97d94-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97d94-107">Attributes and Elements</span></span>  
 <span data-ttu-id="97d94-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97d94-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97d94-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="97d94-109">Attributes</span></span>  
 <span data-ttu-id="97d94-110">None</span><span class="sxs-lookup"><span data-stu-id="97d94-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97d94-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97d94-111">Child Elements</span></span>  
  
|<span data-ttu-id="97d94-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="97d94-112">Element</span></span>|<span data-ttu-id="97d94-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="97d94-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97d94-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="97d94-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="97d94-115">Contiene los valores <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> que configuran los módulos <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP (WSFAM) y (SAM).</span><span class="sxs-lookup"><span data-stu-id="97d94-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97d94-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97d94-116">Parent Elements</span></span>  
 <span data-ttu-id="97d94-117">None</span><span class="sxs-lookup"><span data-stu-id="97d94-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d94-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="97d94-118">Remarks</span></span>  
 <span data-ttu-id="97d94-119">Agregue `<system.identityModel.services>` una sección al archivo de configuración de la aplicación para proporcionar la configuración de SAM y WSFAM.</span><span class="sxs-lookup"><span data-stu-id="97d94-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="97d94-120">Cuando se <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la clase o la para proporcionar control de<xref:System.Security.Claims.ClaimsAuthorizationManager>acceso basado en notificaciones en el código, el administrador de autorización de notificaciones ( ) y la directiva que se usa para tomar decisiones de autorización se configuran a través de un `<identityConfiguration>` elemento al que se hace referencia implícita o explícitamente desde un `<federationConfiguration>` elemento de esta sección.</span><span class="sxs-lookup"><span data-stu-id="97d94-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="97d94-121">Para obtener más información, vea el **Comentarios** en el [ \<federationConfiguration>](federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="97d94-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="97d94-122">La `<system.identityModel.services>` sección está representada <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> por la clase.</span><span class="sxs-lookup"><span data-stu-id="97d94-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="97d94-123">La colección `<federationConfiguration>` de elementos secundarios configurados <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> en la sección se representa mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="97d94-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97d94-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97d94-124">Example</span></span>  
 <span data-ttu-id="97d94-125">El siguiente XML muestra `<system.identityModel.services>` cómo agregar una sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="97d94-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="97d94-126">Primero debe agregar declaraciones de `<system.identityModel.services>` sección `<system.identityModel>` para la sección y las secciones.</span><span class="sxs-lookup"><span data-stu-id="97d94-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="97d94-127">(Al agregar `<system.identityModel.services>` una sección, también debe agregar `<system.identityModel>` una declaración `<identityConfiguration>` para la sección para asegurarse de que el tiempo de ejecución puede crear una sección predeterminada si es necesario.) Una vez agregadas las declaraciones de sección, puede `<system.identityModel.services>` configurar los valores de autenticación federada en el elemento.</span><span class="sxs-lookup"><span data-stu-id="97d94-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
