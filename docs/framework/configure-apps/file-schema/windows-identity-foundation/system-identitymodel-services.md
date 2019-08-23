---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: bef061c5c982fb0e740f889336a3b334bc19225e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943660"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="349ef-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="349ef-102">\<system.identityModel.services></span></span>
<span data-ttu-id="349ef-103">Sección de configuración para la autenticación mediante el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="349ef-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="349ef-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="349ef-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="349ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="349ef-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="349ef-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="349ef-106">Attributes and Elements</span></span>  
 <span data-ttu-id="349ef-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="349ef-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="349ef-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="349ef-108">Attributes</span></span>  
 <span data-ttu-id="349ef-109">None</span><span class="sxs-lookup"><span data-stu-id="349ef-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="349ef-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="349ef-110">Child Elements</span></span>  
  
|<span data-ttu-id="349ef-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="349ef-111">Element</span></span>|<span data-ttu-id="349ef-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="349ef-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="349ef-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="349ef-113">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="349ef-114">Contiene la configuración que configura los <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> módulos http (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> y (SAM).</span><span class="sxs-lookup"><span data-stu-id="349ef-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="349ef-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="349ef-115">Parent Elements</span></span>  
 <span data-ttu-id="349ef-116">None</span><span class="sxs-lookup"><span data-stu-id="349ef-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="349ef-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="349ef-117">Remarks</span></span>  
 <span data-ttu-id="349ef-118">Agregue una `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración de Sam y WSFAM.</span><span class="sxs-lookup"><span data-stu-id="349ef-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="349ef-119">Cuando se usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el administrador de<xref:System.Security.Claims.ClaimsAuthorizationManager>autorización de notificaciones () y la Directiva que se usa para tomar `<identityConfiguration>` decisiones de autorización se configuran mediante un elemento al que se hace referencia de forma implícita o explícita `<federationConfiguration>` desde un elemento de esta sección.</span><span class="sxs-lookup"><span data-stu-id="349ef-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="349ef-120">Para obtener más información, vea las **notas** en el [ \<elemento > de federationConfiguration](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="349ef-120">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="349ef-121">La sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase. `<system.identityModel.services>`</span><span class="sxs-lookup"><span data-stu-id="349ef-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="349ef-122">La colección de elementos `<federationConfiguration>` secundarios configurada en la sección se representa <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="349ef-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="349ef-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="349ef-123">Example</span></span>  
 <span data-ttu-id="349ef-124">El siguiente XML muestra cómo agregar una `<system.identityModel.services>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="349ef-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="349ef-125">Primero debe agregar declaraciones de sección para la `<system.identityModel.services>` sección y las `<system.identityModel>` secciones.</span><span class="sxs-lookup"><span data-stu-id="349ef-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="349ef-126">(Al agregar una `<system.identityModel.services>` sección, también debe agregar una declaración para la `<system.identityModel>` sección para asegurarse de que el tiempo de `<identityConfiguration>` ejecución puede crear una sección predeterminada, si es necesario). Una vez agregadas las declaraciones de sección, puede configurar las opciones de autenticación federada en `<system.identityModel.services>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="349ef-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
