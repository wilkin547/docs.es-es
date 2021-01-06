---
title: 'Seguridad en aplicaciones de gRPC: gRPC para desarrolladores de WCF'
description: Información general sobre la autenticación de llamadas y canales y la autorización en gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: a5c16a4a4f7567e23bf4f9e3049fe116086daf12
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938096"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="d7dfb-103">Seguridad en aplicaciones gRPC</span><span class="sxs-lookup"><span data-stu-id="d7dfb-103">Security in gRPC applications</span></span>

<span data-ttu-id="d7dfb-104">En cualquier escenario real, es fundamental proteger las aplicaciones y los servicios.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-104">In any real-world scenario, securing applications and services are essential.</span></span> <span data-ttu-id="d7dfb-105">La seguridad cubre tres áreas clave:</span><span class="sxs-lookup"><span data-stu-id="d7dfb-105">Security covers three key areas:</span></span>

* <span data-ttu-id="d7dfb-106">Cifrar el tráfico de red para evitar que hackers malintencionados lo intercepten.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="d7dfb-107">Autenticación de clientes y servidores para establecer la identidad y la confianza.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="d7dfb-108">Autorizar a los clientes a controlar el acceso a los sistemas y aplicar permisos basados en la identidad.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="d7dfb-109">La *autenticación* está relacionada con el establecimiento de la identidad de un cliente o un servidor.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="d7dfb-110">La *autorización* se refiere a determinar si un cliente tiene permiso de acceso a un recurso o emitir un comando.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="d7dfb-111">En este capítulo se tratarán los servicios de autenticación y autorización de gRPC para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="d7dfb-112">También se describe la seguridad de red a través de conexiones cifradas TLS.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="d7dfb-113">Autenticación y autorización de WCF</span><span class="sxs-lookup"><span data-stu-id="d7dfb-113">WCF authentication and authorization</span></span>

<span data-ttu-id="d7dfb-114">En Windows Communication Foundation (WCF), la autenticación y la autorización se controlan de maneras diferentes, en función de los transportes y los enlaces que se usan.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="d7dfb-115">WCF admitía varios estándares de WS- \* Security.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="d7dfb-116">También admite la autenticación de Windows para los servicios HTTP que se ejecutan en IIS o en los servicios NetTCP entre sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="d7dfb-117">autenticación y autorización de gRPC</span><span class="sxs-lookup"><span data-stu-id="d7dfb-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="d7dfb-118">la autenticación y autorización de gRPC funciona en dos niveles:</span><span class="sxs-lookup"><span data-stu-id="d7dfb-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="d7dfb-119">La autenticación o autorización de nivel de llamada normalmente se controla a través de tokens que se aplican en los metadatos cuando se realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="d7dfb-120">La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="d7dfb-121">También puede incluir credenciales de autenticación y autorización de nivel de llamada para que se apliquen a cada llamada en el canal automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="d7dfb-122">Puede usar uno de estos mecanismos o ambos para ayudar a proteger su servicio.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="d7dfb-123">La implementación de ASP.NET Core de gRPC admite la autenticación y la autorización a través de la mayoría de los mecanismos de ASP.NET Core estándar:</span><span class="sxs-lookup"><span data-stu-id="d7dfb-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="d7dfb-124">Autenticación de llamadas</span><span class="sxs-lookup"><span data-stu-id="d7dfb-124">Call authentication</span></span>
  - <span data-ttu-id="d7dfb-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d7dfb-125">Azure Active Directory</span></span>
  - <span data-ttu-id="d7dfb-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="d7dfb-126">IdentityServer</span></span>
  - <span data-ttu-id="d7dfb-127">Token de portador JWT</span><span class="sxs-lookup"><span data-stu-id="d7dfb-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="d7dfb-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="d7dfb-128">OAuth 2.0</span></span>
  - <span data-ttu-id="d7dfb-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="d7dfb-129">OpenID Connect</span></span>
  - <span data-ttu-id="d7dfb-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="d7dfb-130">WS-Federation</span></span>
- <span data-ttu-id="d7dfb-131">Autenticación de canal</span><span class="sxs-lookup"><span data-stu-id="d7dfb-131">Channel authentication</span></span>
  - <span data-ttu-id="d7dfb-132">Certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="d7dfb-132">Client certificate</span></span>

<span data-ttu-id="d7dfb-133">Los métodos de autenticación de llamada se basan en *tokens*.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="d7dfb-134">La única diferencia real es la forma en que se generan los tokens y las bibliotecas que se usan para validar los tokens en el servicio de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="d7dfb-135">Para obtener más información, consulte el artículo sobre [autenticación y autorización](/aspnet/core/grpc/authn-and-authz) .</span><span class="sxs-lookup"><span data-stu-id="d7dfb-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="d7dfb-136">Cuando se usa gRPC a través de una conexión HTTP/2 cifrada con TLS, todo el tráfico entre los clientes y los servidores se cifra, incluso si no se usa la autenticación de nivel de canal.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="d7dfb-137">En este capítulo se muestra cómo aplicar credenciales de llamada y de canal a un servicio de gRPC.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="d7dfb-138">También se muestra cómo usar las credenciales de un cliente gRPC de .NET para autenticarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="d7dfb-138">It will also show how to use credentials from a .NET gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d7dfb-139">[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="d7dfb-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
