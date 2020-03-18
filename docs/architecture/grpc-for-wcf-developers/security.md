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
# <a name="security-in-grpc-applications"></a>Seguridad en aplicaciones gRPC

En cualquier escenario del mundo real, es esencial proteger aplicaciones y servicios. La seguridad abarca tres áreas clave:

* Cifrar el tráfico de red para evitar que los piratas informáticos malintencionados lo intercepten.
* Autenticar clientes y servidores para establecer identidad y confianza.
* Autorizar a los clientes para controlar el acceso a los sistemas y aplicar permisos en función de la identidad.

> [!NOTE]
> *La autenticación* se refiere a establecer la identidad de un cliente o servidor. *La autorización* se refiere a determinar si un cliente tiene permiso para acceder a un recurso o emitir un comando.

Este capítulo cubrirá las facilidades para la autenticación y autorización en gRPC para ASP.NET Core. También discutirá la seguridad de la red a través de conexiones cifradas TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticación y autorización de WCF

En Windows Communication Foundation (WCF), la autenticación y la autorización se controlaban de diferentes maneras, en función de los transportes y enlaces que se usaban. WCF admite varios\* estándares de seguridad WS. También admite la autenticación de Windows para servicios HTTP que se ejecutan en servicios IIS o NetTCP entre sistemas Windows.

## <a name="grpc-authentication-and-authorization"></a>Autenticación y autorización gRPC

La autenticación y autorización gRPC funciona en dos niveles:

* La autenticación/autorización de nivel de llamada se controla normalmente a través de tokens que se aplican en los metadatos cuando se realiza la llamada.
* La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión. También puede incluir credenciales de autenticación/autorización de nivel de llamada que se aplicarán automáticamente a cada llamada en el canal.

Puede utilizar uno o ambos de estos mecanismos para ayudar a proteger su servicio.

La implementación ASP.NET Core de gRPC admite la autenticación y autorización a través de la mayoría de los mecanismos estándar de ASP.NET Core:

- Autenticación de llamadas
  - Azure Active Directory
  - IdentityServer
  - JWT Bearer Token
  - OAuth 2.0
  - OpenID Connect
  - El certificado del proveedor de identidades de WS-Federation
- Autenticación de canal
  - Certificado de cliente

Todos los métodos de autenticación de llamadas se basan en *tokens.* La única diferencia real es cómo se generan los tokens y las bibliotecas que se usan para validar los tokens en el servicio ASP.NET Core.

Para obtener más información, consulte el artículo [Autenticación y autorización.](/aspnet/core/grpc/authn-and-authz)

> [!NOTE]
> Cuando se usa gRPC a través de una conexión HTTP/2 cifrada por TLS, todo el tráfico entre clientes y servidores se cifra, incluso si no se utiliza la autenticación a nivel de canal.

Este capítulo mostrará cómo aplicar credenciales de llamada y credenciales de canal a un servicio gRPC. También mostrará cómo usar credenciales de un cliente gRPC de .NET Core para autenticarse con el servicio.

>[!div class="step-by-step"]
>[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)
