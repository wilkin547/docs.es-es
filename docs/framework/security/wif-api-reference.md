---
title: Referencia de API de WIF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d7ae7ef82d12c024441d01ef420bc9366e3c589d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wif-api-reference"></a><span data-ttu-id="1e457-102">Referencia de API de WIF</span><span class="sxs-lookup"><span data-stu-id="1e457-102">WIF API Reference</span></span>
<span data-ttu-id="1e457-103">Las clases de Windows Identity Foundation (WIF) se dividen entre los siguientes ensamblados: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) y `System.ServiceModel` (System.ServiceModel.dll).</span><span class="sxs-lookup"><span data-stu-id="1e457-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="1e457-104">Este tema proporciona vínculos a los espacios de nombres de WIF e incluye breves explicaciones de las clases que contiene cada espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1e457-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e457-105">Los siguientes espacios de nombres `System.IdentityModel` contienen clases que implementan el modelo de identidad basado en notificaciones de WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> y <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e457-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1e457-106">A partir de .NET Framework 4.5, el modelo de identidad basado en notificaciones de WCF se reemplaza por WIF.</span><span class="sxs-lookup"><span data-stu-id="1e457-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="1e457-107">No debe utilizar clases en estos tres espacios de nombres cuando compile soluciones basadas en WIF.</span><span class="sxs-lookup"><span data-stu-id="1e457-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-108">Contiene clases que representan las transformaciones de cookies, los servicios de token de seguridad y los lectores de diccionario XML especializados.</span><span class="sxs-lookup"><span data-stu-id="1e457-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-109">Contiene clases que proporcionan la configuración para las aplicaciones y los servicios creados con Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="1e457-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="1e457-110">Las clases de este espacio de nombres representan la configuración del elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).</span><span class="sxs-lookup"><span data-stu-id="1e457-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-111">Contiene clases que representan los elementos de un documento de metadatos de federación.</span><span class="sxs-lookup"><span data-stu-id="1e457-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-112">Contiene clases que representan artefactos de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="1e457-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-113">Contiene clases que se usan en escenarios pasivos (WS-Federation).</span><span class="sxs-lookup"><span data-stu-id="1e457-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="1e457-114">También contiene algunas clases que representan la configuración del elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e457-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="1e457-115">La configuración de este elemento configura WS-Federation para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1e457-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="1e457-116">El espacio de nombres `System.IdentityModel.Services.Configuration` contiene la mayoría de las clases que se usan para configurar WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="1e457-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-117">Contiene clases que proporcionan la configuración para las aplicaciones de WIF que usan el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="1e457-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="1e457-118">Las clases de este espacio de nombres representan la configuración del elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e457-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="1e457-119">El espacio de nombres `System.IdentityModel.Services` además contiene algunas clases que se usan para configurar WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="1e457-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-120">Contiene controladores de tokens de seguridad especializados para escenarios de granja de servidores web.</span><span class="sxs-lookup"><span data-stu-id="1e457-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-121">Contiene clases que representan tokens de seguridad, controladores de tokens de seguridad y otros artefactos de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1e457-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-122">Contiene clases que representan notificaciones, identidades basadas en notificaciones, entidades de seguridad basadas en notificaciones y otros artefactos del modelo de identidad basado en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="1e457-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="1e457-123">Contiene clases que representan contratos de WCF, canales, hosts de servicio y otros artefactos que se usan en escenarios activos (WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="1e457-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="1e457-124">Este espacio de nombres además contiene clases que son específicas de Windows Communication Foundation (WCF) y que WIF no usa.</span><span class="sxs-lookup"><span data-stu-id="1e457-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e457-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e457-125">See Also</span></span>  
 [<span data-ttu-id="1e457-126">Referencia de configuración de WIF</span><span class="sxs-lookup"><span data-stu-id="1e457-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)  
 [<span data-ttu-id="1e457-127">Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="1e457-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
