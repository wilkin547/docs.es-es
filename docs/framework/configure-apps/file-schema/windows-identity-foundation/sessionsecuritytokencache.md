---
description: 'Más información acerca de: <sessionSecurityTokenCache>'
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 6fc0bb518f546ffd80c68df95a9c0fab145423b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698289"
---
# \<sessionSecurityTokenCache>

<span data-ttu-id="f6c6e-102">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6c6e-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="f6c6e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6c6e-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6c6e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f6c6e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f6c6e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f6c6e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6c6e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="f6c6e-106">Attributes</span></span>  
  
|<span data-ttu-id="f6c6e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="f6c6e-107">Attribute</span></span>|<span data-ttu-id="f6c6e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6c6e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6c6e-109">type</span><span class="sxs-lookup"><span data-stu-id="f6c6e-109">type</span></span>|<span data-ttu-id="f6c6e-110">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="f6c6e-110">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6c6e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f6c6e-111">Child Elements</span></span>  

 <span data-ttu-id="f6c6e-112">None</span><span class="sxs-lookup"><span data-stu-id="f6c6e-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6c6e-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f6c6e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f6c6e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6c6e-114">Element</span></span>|<span data-ttu-id="f6c6e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6c6e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="f6c6e-116">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6c6e-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f6c6e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6c6e-117">Example</span></span>  

 <span data-ttu-id="f6c6e-118">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad de la sesión ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="f6c6e-118">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="f6c6e-119">La configuración se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f6c6e-119">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="f6c6e-120">Para obtener más información sobre este ejemplo, consulte [Índice de ejemplo de código WIF](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="f6c6e-120">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6c6e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6c6e-121">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
