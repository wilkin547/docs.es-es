---
description: 'Más información acerca de: <System. identityModel. Services>'
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 037a96c2620e06ef6aed85d1dbaba62aca72e9eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786556"
---
# \<system.identityModel.services>

<span data-ttu-id="b66a1-103">Sección de configuración para la autenticación mediante el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="b66a1-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
## <a name="syntax"></a><span data-ttu-id="b66a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b66a1-104">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b66a1-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b66a1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b66a1-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b66a1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b66a1-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b66a1-107">Attributes</span></span>  

 <span data-ttu-id="b66a1-108">None</span><span class="sxs-lookup"><span data-stu-id="b66a1-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b66a1-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b66a1-109">Child Elements</span></span>  
  
|<span data-ttu-id="b66a1-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="b66a1-110">Element</span></span>|<span data-ttu-id="b66a1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b66a1-111">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="b66a1-112">Contiene la configuración que configura los <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> módulos http (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="b66a1-112">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b66a1-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b66a1-113">Parent Elements</span></span>  

 <span data-ttu-id="b66a1-114">None</span><span class="sxs-lookup"><span data-stu-id="b66a1-114">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b66a1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b66a1-115">Remarks</span></span>  

 <span data-ttu-id="b66a1-116">Agregue una `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración de Sam y WSFAM.</span><span class="sxs-lookup"><span data-stu-id="b66a1-116">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b66a1-117">Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el administrador de autorización de notificaciones ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) y la Directiva que se usa para tomar decisiones de autorización se configuran mediante un `<identityConfiguration>` elemento al que se hace referencia de forma implícita o explícita desde un `<federationConfiguration>` elemento de esta sección.</span><span class="sxs-lookup"><span data-stu-id="b66a1-117">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="b66a1-118">Para obtener más información, vea las **notas** del [\<federationConfiguration>](federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b66a1-118">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="b66a1-119">La `<system.identityModel.services>` sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase.</span><span class="sxs-lookup"><span data-stu-id="b66a1-119">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="b66a1-120">La colección de `<federationConfiguration>` elementos secundarios configurada en la sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="b66a1-120">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b66a1-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b66a1-121">Example</span></span>  

 <span data-ttu-id="b66a1-122">El siguiente XML muestra cómo agregar una `<system.identityModel.services>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b66a1-122">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="b66a1-123">Primero debe agregar declaraciones de sección para la `<system.identityModel.services>` sección y las `<system.identityModel>` secciones.</span><span class="sxs-lookup"><span data-stu-id="b66a1-123">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="b66a1-124">(Al agregar una `<system.identityModel.services>` sección, también debe agregar una declaración para la `<system.identityModel>` sección para asegurarse de que `<identityConfiguration>` el tiempo de ejecución puede crear una sección predeterminada, si es necesario). Una vez agregadas las declaraciones de sección, puede configurar las opciones de autenticación federada en el `<system.identityModel.services>` elemento.</span><span class="sxs-lookup"><span data-stu-id="b66a1-124">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
