---
title: 'Seguridad en aplicaciones de gRPC: gRPC para desarrolladores de WCF'
description: Información general sobre la autenticación de llamadas y canales y la autorización en gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841376"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="ab316-103">Seguridad en aplicaciones gRPC</span><span class="sxs-lookup"><span data-stu-id="ab316-103">Security in gRPC applications</span></span>

<span data-ttu-id="ab316-104">En cualquier escenario real, es fundamental proteger las aplicaciones y los servicios.</span><span class="sxs-lookup"><span data-stu-id="ab316-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="ab316-105">La seguridad cubre tres áreas clave: el cifrado del tráfico de red para evitar que lo intercepten actores no válidos. autenticación de clientes y servidores para establecer la identidad y la confianza; y autorizar a los clientes para controlar el acceso a los sistemas y aplicar permisos basados en la identidad.</span><span class="sxs-lookup"><span data-stu-id="ab316-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="ab316-106">La **autenticación** está relacionada con el establecimiento de la identidad de un cliente o un servidor.</span><span class="sxs-lookup"><span data-stu-id="ab316-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="ab316-107">La **autorización** se refiere a determinar si un cliente tiene permiso de acceso a un recurso o emitir un comando.</span><span class="sxs-lookup"><span data-stu-id="ab316-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="ab316-108">En este capítulo se tratarán los servicios de autenticación y autorización de gRPC para ASP.NET Core y se explicará la seguridad de red mediante conexiones cifradas TLS.</span><span class="sxs-lookup"><span data-stu-id="ab316-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="ab316-109">Autenticación y autorización de WCF</span><span class="sxs-lookup"><span data-stu-id="ab316-109">WCF authentication and authorization</span></span>

<span data-ttu-id="ab316-110">En WCF, la autenticación y la autorización se trataban de maneras diferentes en función de los transportes y los enlaces que se usan.</span><span class="sxs-lookup"><span data-stu-id="ab316-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="ab316-111">WCF admite diversos estándares de seguridad de WS-\*, así como la autenticación de Windows para los servicios HTTP que se ejecutan en IIS o en servicios de NetTCP entre sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="ab316-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="ab316-112">autenticación y autorización de gRPC</span><span class="sxs-lookup"><span data-stu-id="ab316-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="ab316-113">la autenticación y autorización de gRPC funciona en dos niveles.</span><span class="sxs-lookup"><span data-stu-id="ab316-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="ab316-114">La autenticación o autorización de nivel de llamada normalmente se controla mediante tokens que se aplican en los metadatos cuando se realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ab316-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="ab316-115">La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión y también puede incluir credenciales de autenticación y autorización de nivel de llamada para que se apliquen a cada llamada en el canal automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ab316-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="ab316-116">Puede usar uno de estos mecanismos o ambos para proteger su servicio.</span><span class="sxs-lookup"><span data-stu-id="ab316-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="ab316-117">La implementación de ASP.NET Core de gRPC admite la autenticación y autorización mediante la mayoría de los mecanismos de ASP.NET Core estándar:</span><span class="sxs-lookup"><span data-stu-id="ab316-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="ab316-118">Autenticación de llamadas</span><span class="sxs-lookup"><span data-stu-id="ab316-118">Call authentication</span></span>
  - <span data-ttu-id="ab316-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab316-119">Azure Active Directory</span></span>
  - <span data-ttu-id="ab316-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="ab316-120">IdentityServer</span></span>
  - <span data-ttu-id="ab316-121">Token de portador JWT</span><span class="sxs-lookup"><span data-stu-id="ab316-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="ab316-122">OAuth 2,0</span><span class="sxs-lookup"><span data-stu-id="ab316-122">OAuth 2.0</span></span>
  - <span data-ttu-id="ab316-123">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="ab316-123">OpenID Connect</span></span>
  - <span data-ttu-id="ab316-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="ab316-124">WS-Federation</span></span>
- <span data-ttu-id="ab316-125">Autenticación de canal</span><span class="sxs-lookup"><span data-stu-id="ab316-125">Channel authentication</span></span>
  - <span data-ttu-id="ab316-126">Certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="ab316-126">Client Certificate</span></span>

<span data-ttu-id="ab316-127">Los métodos de autenticación de llamada se basan en *tokens*.</span><span class="sxs-lookup"><span data-stu-id="ab316-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="ab316-128">La única diferencia real es cómo se genera el token y las bibliotecas que se usan para validar los tokens en el servicio de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab316-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="ab316-129">Para obtener más información, consulte la [documentación de autenticación y autorización en Microsoft docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="ab316-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="ab316-130">Cuando se usa gRPC a través de una conexión HTTP/2 cifrada con TLS, todo el tráfico entre los clientes y los servidores se cifra, incluso si no se usa la autenticación de nivel de canal.</span><span class="sxs-lookup"><span data-stu-id="ab316-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="ab316-131">En este capítulo se muestra cómo aplicar credenciales de llamada y de canal a un servicio de gRPC y cómo usar las credenciales de un cliente de gRPC de .NET Core para autenticarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="ab316-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ab316-132">[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="ab316-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
