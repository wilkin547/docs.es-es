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
# <a name="security-in-grpc-applications"></a>Seguridad en aplicaciones gRPC

En cualquier escenario real, es fundamental proteger las aplicaciones y los servicios. La seguridad cubre tres áreas clave: el cifrado del tráfico de red para evitar que lo intercepten actores no válidos. autenticación de clientes y servidores para establecer la identidad y la confianza; y autorizar a los clientes para controlar el acceso a los sistemas y aplicar permisos basados en la identidad.

> [!NOTE]
> La **autenticación** está relacionada con el establecimiento de la identidad de un cliente o un servidor. La **autorización** se refiere a determinar si un cliente tiene permiso de acceso a un recurso o emitir un comando.

En este capítulo se tratarán los servicios de autenticación y autorización de gRPC para ASP.NET Core y se explicará la seguridad de red mediante conexiones cifradas TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticación y autorización de WCF

En WCF, la autenticación y la autorización se trataban de maneras diferentes en función de los transportes y los enlaces que se usan. WCF admite diversos estándares de seguridad de WS-\*, así como la autenticación de Windows para los servicios HTTP que se ejecutan en IIS o en servicios de NetTCP entre sistemas Windows.

## <a name="grpc-authentication-and-authorization"></a>autenticación y autorización de gRPC

la autenticación y autorización de gRPC funciona en dos niveles. La autenticación o autorización de nivel de llamada normalmente se controla mediante tokens que se aplican en los metadatos cuando se realiza la llamada. La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión y también puede incluir credenciales de autenticación y autorización de nivel de llamada para que se apliquen a cada llamada en el canal automáticamente. Puede usar uno de estos mecanismos o ambos para proteger su servicio.

La implementación de ASP.NET Core de gRPC admite la autenticación y autorización mediante la mayoría de los mecanismos de ASP.NET Core estándar:

- Autenticación de llamadas
  - Azure Active Directory
  - IdentityServer
  - Token de portador JWT
  - OAuth 2,0
  - OpenID Connect
  - WS-Federation
- Autenticación de canal
  - Certificado de cliente

Los métodos de autenticación de llamada se basan en *tokens*. La única diferencia real es cómo se genera el token y las bibliotecas que se usan para validar los tokens en el servicio de ASP.NET Core.

Para obtener más información, consulte la [documentación de autenticación y autorización en Microsoft docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).

> [!NOTE]
> Cuando se usa gRPC a través de una conexión HTTP/2 cifrada con TLS, todo el tráfico entre los clientes y los servidores se cifra, incluso si no se usa la autenticación de nivel de canal.

En este capítulo se muestra cómo aplicar credenciales de llamada y de canal a un servicio de gRPC y cómo usar las credenciales de un cliente de gRPC de .NET Core para autenticarse con el servicio.

>[!div class="step-by-step"]
>[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)
