---
title: Seguridad en aplicaciones gRPC - gRPC para desarrolladores de WCF
description: Descripción general de la autenticación y autorización de llamadas y canales en gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147820"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="33522-103">Seguridad en aplicaciones gRPC</span><span class="sxs-lookup"><span data-stu-id="33522-103">Security in gRPC applications</span></span>

<span data-ttu-id="33522-104">En cualquier escenario del mundo real, es esencial proteger aplicaciones y servicios.</span><span class="sxs-lookup"><span data-stu-id="33522-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="33522-105">La seguridad abarca tres áreas clave:</span><span class="sxs-lookup"><span data-stu-id="33522-105">Security covers three key areas:</span></span>

* <span data-ttu-id="33522-106">Cifrar el tráfico de red para evitar que los piratas informáticos malintencionados lo intercepten.</span><span class="sxs-lookup"><span data-stu-id="33522-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="33522-107">Autenticar clientes y servidores para establecer identidad y confianza.</span><span class="sxs-lookup"><span data-stu-id="33522-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="33522-108">Autorizar a los clientes para controlar el acceso a los sistemas y aplicar permisos en función de la identidad.</span><span class="sxs-lookup"><span data-stu-id="33522-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="33522-109">*La autenticación* se refiere a establecer la identidad de un cliente o servidor.</span><span class="sxs-lookup"><span data-stu-id="33522-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="33522-110">*La autorización* se refiere a determinar si un cliente tiene permiso para acceder a un recurso o emitir un comando.</span><span class="sxs-lookup"><span data-stu-id="33522-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="33522-111">Este capítulo cubrirá las facilidades para la autenticación y autorización en gRPC para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="33522-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="33522-112">También discutirá la seguridad de la red a través de conexiones cifradas TLS.</span><span class="sxs-lookup"><span data-stu-id="33522-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="33522-113">Autenticación y autorización de WCF</span><span class="sxs-lookup"><span data-stu-id="33522-113">WCF authentication and authorization</span></span>

<span data-ttu-id="33522-114">En Windows Communication Foundation (WCF), la autenticación y la autorización se controlaban de diferentes maneras, en función de los transportes y enlaces que se usaban.</span><span class="sxs-lookup"><span data-stu-id="33522-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="33522-115">WCF admite varios\* estándares de seguridad WS.</span><span class="sxs-lookup"><span data-stu-id="33522-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="33522-116">También admite la autenticación de Windows para servicios HTTP que se ejecutan en servicios IIS o NetTCP entre sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="33522-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="33522-117">Autenticación y autorización gRPC</span><span class="sxs-lookup"><span data-stu-id="33522-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="33522-118">La autenticación y autorización gRPC funciona en dos niveles:</span><span class="sxs-lookup"><span data-stu-id="33522-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="33522-119">La autenticación/autorización de nivel de llamada se controla normalmente a través de tokens que se aplican en los metadatos cuando se realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="33522-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="33522-120">La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión.</span><span class="sxs-lookup"><span data-stu-id="33522-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="33522-121">También puede incluir credenciales de autenticación/autorización de nivel de llamada que se aplicarán automáticamente a cada llamada en el canal.</span><span class="sxs-lookup"><span data-stu-id="33522-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="33522-122">Puede utilizar uno o ambos de estos mecanismos para ayudar a proteger su servicio.</span><span class="sxs-lookup"><span data-stu-id="33522-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="33522-123">La implementación ASP.NET Core de gRPC admite la autenticación y autorización a través de la mayoría de los mecanismos estándar de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="33522-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="33522-124">Autenticación de llamadas</span><span class="sxs-lookup"><span data-stu-id="33522-124">Call authentication</span></span>
  - <span data-ttu-id="33522-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="33522-125">Azure Active Directory</span></span>
  - <span data-ttu-id="33522-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="33522-126">IdentityServer</span></span>
  - <span data-ttu-id="33522-127">JWT Bearer Token</span><span class="sxs-lookup"><span data-stu-id="33522-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="33522-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="33522-128">OAuth 2.0</span></span>
  - <span data-ttu-id="33522-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="33522-129">OpenID Connect</span></span>
  - <span data-ttu-id="33522-130">El certificado del proveedor de identidades de WS-Federation</span><span class="sxs-lookup"><span data-stu-id="33522-130">WS-Federation</span></span>
- <span data-ttu-id="33522-131">Autenticación de canal</span><span class="sxs-lookup"><span data-stu-id="33522-131">Channel authentication</span></span>
  - <span data-ttu-id="33522-132">Certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="33522-132">Client certificate</span></span>

<span data-ttu-id="33522-133">Todos los métodos de autenticación de llamadas se basan en *tokens.*</span><span class="sxs-lookup"><span data-stu-id="33522-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="33522-134">La única diferencia real es cómo se generan los tokens y las bibliotecas que se usan para validar los tokens en el servicio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="33522-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="33522-135">Para obtener más información, consulte el artículo [Autenticación y autorización.](/aspnet/core/grpc/authn-and-authz)</span><span class="sxs-lookup"><span data-stu-id="33522-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="33522-136">Cuando se usa gRPC a través de una conexión HTTP/2 cifrada por TLS, todo el tráfico entre clientes y servidores se cifra, incluso si no se utiliza la autenticación a nivel de canal.</span><span class="sxs-lookup"><span data-stu-id="33522-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="33522-137">Este capítulo mostrará cómo aplicar credenciales de llamada y credenciales de canal a un servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="33522-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="33522-138">También mostrará cómo usar credenciales de un cliente gRPC de .NET Core para autenticarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="33522-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="33522-139">[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="33522-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
