---
title: 'Seguridad en aplicaciones de gRPC: gRPC para desarrolladores de WCF'
description: Información general sobre la autenticación de llamadas y canales y la autorización en gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503410"
---
# <a name="security-in-grpc-applications"></a>Seguridad en aplicaciones gRPC

En cualquier escenario real, es fundamental proteger las aplicaciones y los servicios. La seguridad cubre tres áreas clave: 

* Cifrar el tráfico de red para evitar que hackers malintencionados lo intercepten.
* Autenticación de clientes y servidores para establecer la identidad y la confianza.
* Autorizar a los clientes a controlar el acceso a los sistemas y aplicar permisos basados en la identidad.

> [!NOTE]
> La *autenticación* está relacionada con el establecimiento de la identidad de un cliente o un servidor. La *autorización* se refiere a determinar si un cliente tiene permiso de acceso a un recurso o emitir un comando.

En este capítulo se tratarán los servicios de autenticación y autorización de gRPC para ASP.NET Core. También se describe la seguridad de red a través de conexiones cifradas TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticación y autorización de WCF

En Windows Communication Foundation (WCF), la autenticación y la autorización se controlan de maneras diferentes, en función de los transportes y los enlaces que se usan. WCF admite diversos estándares de seguridad de WS-\*. También admite la autenticación de Windows para los servicios HTTP que se ejecutan en IIS o en los servicios NetTCP entre sistemas Windows.

## <a name="grpc-authentication-and-authorization"></a>autenticación y autorización de gRPC

la autenticación y autorización de gRPC funciona en dos niveles:

* La autenticación o autorización de nivel de llamada normalmente se controla a través de tokens que se aplican en los metadatos cuando se realiza la llamada. 
* La autenticación de nivel de canal utiliza un certificado de cliente que se aplica en el nivel de conexión. También puede incluir credenciales de autenticación y autorización de nivel de llamada para que se apliquen a cada llamada en el canal automáticamente. 

Puede usar uno de estos mecanismos o ambos para ayudar a proteger su servicio.

La implementación de ASP.NET Core de gRPC admite la autenticación y la autorización a través de la mayoría de los mecanismos de ASP.NET Core estándar:

- Autenticación de llamadas
  - Azure Active Directory
  - IdentityServer
  - Token de portador JWT
  - OAuth 2.0
  - OpenID Connect
  - El certificado del proveedor de identidades de WS-Federation
- Autenticación de canal
  - Certificado de cliente

Los métodos de autenticación de llamada se basan en *tokens*. La única diferencia real es la forma en que se generan los tokens y las bibliotecas que se usan para validar los tokens en el servicio de ASP.NET Core.

Para obtener más información, consulte el artículo sobre [autenticación y autorización](/aspnet/core/grpc/authn-and-authz) .

> [!NOTE]
> Cuando se usa gRPC a través de una conexión HTTP/2 cifrada con TLS, todo el tráfico entre los clientes y los servidores se cifra, incluso si no se usa la autenticación de nivel de canal.

En este capítulo se muestra cómo aplicar credenciales de llamada y de canal a un servicio de gRPC. También se muestra cómo usar las credenciales de un cliente gRPC de .NET Core para autenticarse con el servicio.

>[!div class="step-by-step"]
>[Anterior](client-libraries.md)
>[Siguiente](call-credentials.md)
