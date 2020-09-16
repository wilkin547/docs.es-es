---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 4169fe307e9ef7c391500a2292fcc247f435caa9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555892"
---
# \<sessionSecurityTokenCache>
<span data-ttu-id="a60ca-101">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a60ca-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="a60ca-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a60ca-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a60ca-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a60ca-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a60ca-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a60ca-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a60ca-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="a60ca-105">Attributes</span></span>  
  
|<span data-ttu-id="a60ca-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="a60ca-106">Attribute</span></span>|<span data-ttu-id="a60ca-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a60ca-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a60ca-108">type</span><span class="sxs-lookup"><span data-stu-id="a60ca-108">type</span></span>|<span data-ttu-id="a60ca-109">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="a60ca-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a60ca-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a60ca-110">Child Elements</span></span>  
 <span data-ttu-id="a60ca-111">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a60ca-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a60ca-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a60ca-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a60ca-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a60ca-113">Element</span></span>|<span data-ttu-id="a60ca-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a60ca-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="a60ca-115">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a60ca-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a60ca-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a60ca-116">Example</span></span>  
 <span data-ttu-id="a60ca-117">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad de la sesión ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="a60ca-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="a60ca-118">La configuración se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a60ca-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="a60ca-119">Para obtener más información sobre este ejemplo, consulte [Índice de ejemplo de código WIF](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="a60ca-119">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a60ca-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a60ca-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
