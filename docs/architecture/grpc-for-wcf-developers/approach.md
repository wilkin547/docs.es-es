---
title: Cómo gRPC se aproxima a RPC-gRPC para desarrolladores de WCF
description: Comparar las características clave de WCF con gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 3da28968f8c8bd6c4fdba7432ffc8458d8340457
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841694"
---
# <a name="how-grpc-approaches-rpc"></a>Procedimiento de gRPC para abordar RPC

Windows Communication Foundation (WCF) y gRPC son implementaciones del patrón *llamada a procedimiento remoto* (RPC), que pretende realizar llamadas a servicios que se ejecutan en un equipo diferente o en un proceso diferente, trabajar sin problemas como si fueran simplemente llamadas a métodos en la aplicación cliente. Aunque los objetivos de WCF y gRPC son los mismos, los detalles de la implementación son bastante diferentes.

En la tabla siguiente se describe cómo se relacionan las características clave de WCF con gRPC y dónde se pueden encontrar explicaciones más detalladas en el resto del libro.

| Características | WCF | gRPC |
| -------- | --- | ---- |
| Objetivo | Separar el código empresarial de la implementación de redes | Separe el código empresarial de la definición de la interfaz y de la implementación de redes |
| Definir servicios y mensajes (capítulo 3-4)  | Contrato de servicio, contrato de operación y contrato de datos | Usa el archivo proto para declarar servicios y mensajes |
| Idioma (capítulo 3-5) | Contratos escritos en C# o Visual Basic | Lenguaje de búfer de protocolo |
| Formato de conexión (capítulo 3) | Configurable, incluido SOAP/XML, XML sin formato, JSON, binario .NET, etc. | Formato binario de búfer de protocolo (aunque es posible usar otros formatos).
| Interoperabilidad (capítulo 4) | Al usar SOAP a través de HTTP | Compatibilidad oficial: .NET, Java, Python, JavaScript, C/C++, Go, oxidate, Ruby, SWIFT, DART y php. Compatibilidad no oficial para otros idiomas de la comunidad. |
| Redes (capítulo 4) | Configurado en tiempo de ejecución. Cambiar entre NetTCP, HTTP, MSMQ, etc. | HTTP/2, actualmente sobre TCP solo con ASP.NET Core gRPC. |
| Enfoque (capítulo 4) | Generación de/deserialization de serialización en tiempo de ejecución y código de red en clases base | Generación en tiempo de compilación de/deserialization de serialización y código de red en clases base |
| Seguridad (capítulo 6) | Autenticación, WS-Security, cifrado de mensajes | Credenciales, seguridad de ASP.NET Core, redes TLS |

>[!div class="step-by-step"]
>[Anterior](grpc-overview.md)
>[Siguiente](interface-definition-language.md)
