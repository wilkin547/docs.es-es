---
title: Cómo gRPC se aproxima a RPC-gRPC para desarrolladores de WCF
description: Comparar las características clave de WCF con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: b924d2f20b54de2d6476a0b27626d5dd7fd0986f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711477"
---
# <a name="how-grpc-approaches-rpc"></a>Procedimiento de gRPC para abordar RPC

Windows Communication Foundation (WCF) y gRPC son implementaciones del patrón *llamada a procedimiento remoto* (RPC). Este patrón pretende realizar llamadas a servicios que se ejecutan en un equipo diferente o en un proceso diferente, funcionan sin problemas, como llamadas a métodos en la aplicación cliente. Aunque los objetivos de WCF y gRPC son los mismos, los detalles de la implementación son bastante diferentes.

En la tabla siguiente se describe cómo se relacionan las características clave de WCF con gRPC y dónde se pueden encontrar explicaciones más detalladas.

| Características | WCF | gRPC |
| -------- | --- | ---- |
| Objetivo | Separe el código empresarial de la implementación de redes. | Separe el código empresarial de la definición de la interfaz y de la implementación de redes. |
| Definir servicios y mensajes (capítulos 3-4)  | Contrato de servicio, contrato de operación y contrato de datos. | Usa el archivo proto para declarar servicios y mensajes. |
| Idioma (capítulos 3-5) | Contratos escritos en C# o Visual Basic. | Lenguaje de búfer de protocolo. |
| Formato de conexión (capítulo 3) | Configurable, incluido SOAP/XML, XML sin formato, JSON y binario .NET. | Formato binario de búfer de protocolo (aunque es posible usar otros formatos).
| Interoperabilidad (capítulo 4) | Cuando se utiliza SOAP sobre HTTP. | Compatibilidad oficial: .NET, Java, Python, JavaScript, C/C++, Go, oxidate, Ruby, SWIFT, DART y php. Compatibilidad no oficial para otros idiomas de la comunidad. |
| Redes (capítulo 4) | Configurado en tiempo de ejecución. Cambiar entre NetTCP, HTTP y MSMQ. | HTTP/2, actualmente sobre TCP solo con ASP.NET Core gRPC. |
| Enfoque (capítulo 4) | Generación en tiempo de ejecución de serialización, deserialización y código de red en clases base. | Generación en tiempo de compilación de serialización, deserialización y código de red en clases base. |
| Seguridad (capítulo 6) | Autenticación, WS-Security, cifrado de mensajes. | Credenciales, seguridad de ASP.NET Core, redes TLS. |

>[!div class="step-by-step"]
>[Anterior](grpc-overview.md)
>[Siguiente](interface-definition-language.md)
