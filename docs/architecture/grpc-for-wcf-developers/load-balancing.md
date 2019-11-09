---
title: Equilibrio de carga gRPC-gRPC para desarrolladores de WCF
description: Elección de un equilibrador de carga para trabajar con gRPC Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841556"
---
# <a name="load-balancing-grpc"></a>Equilibrio de carga gRPC

Una implementación típica de una aplicación de gRPC incluye varias instancias idénticas del servicio, lo que proporciona resistencia y escalabilidad horizontal. Equilibrio de carga de las solicitudes entrantes distribuidas entre estas instancias para proporcionar el uso completo de todos los recursos disponibles. Para que este equilibrio de carga sea invisible para el cliente, es habitual usar un servidor de equilibrador de carga de proxy para controlar las solicitudes de los clientes y enrutarlas a las instancias de back-end.

Los equilibradores de carga se clasifican según la *capa* en la que operan. Los equilibradores de carga de nivel 4 funcionan en el nivel de *transporte* , por ejemplo, con Sockets TCP, conexiones y paquetes. Los equilibradores de carga de nivel 7 funcionan en el nivel de *aplicación* , y controlan específicamente las solicitudes HTTP/2 para las aplicaciones gRPC.

## <a name="l4-load-balancers"></a>Equilibradores de carga L4

Un equilibrador de carga L4 acepta una solicitud de conexión TCP de un cliente, abre otra conexión a una de las instancias de back-end y copia los datos entre las dos conexiones sin ningún procesamiento real. L4 ofrece un rendimiento excelente y una baja latencia, pero muy poco control o inteligencia. Siempre que el cliente mantenga abierta la conexión, todas las solicitudes se dirigirán a la misma instancia de back-end.

Un ejemplo de un equilibrador de carga L4 es el [Azure load balancer](https://azure.microsoft.com/services/load-balancer/).

## <a name="l7-load-balancers"></a>Equilibradores de carga L7

Un equilibrador de carga L7 analiza las solicitudes HTTP/2 entrantes y las pasa a las instancias de back-end de manera solicitada, independientemente de cuánto tiempo tenga la conexión el cliente.

Los ejemplos de equilibradores de carga L7 incluyen:

- [Nginx](https://www.nginx.com/)
- [HAproxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Como regla general, los equilibradores de carga L7 son la mejor opción para gRPC y otras aplicaciones HTTP/2 (y, por lo general, para las aplicaciones HTTP). Los equilibradores de carga L4 *funcionarán* con las aplicaciones de gRPC, pero son especialmente útiles cuando la baja latencia y la sobrecarga baja son de primordial importancia.

> [!IMPORTANT]
> En el momento de redactar este documento, no todos los equilibradores de carga L7 admiten todas las partes de la especificación HTTP/2 requerida por gRPC Services, como los encabezados finales.

Cuando se usa el cifrado TLS, los equilibradores de carga pueden finalizar la conexión TLS y pasar las solicitudes no cifradas a la aplicación back-end, o bien pasar la solicitud cifrada. En cualquier caso, el equilibrador de carga tendrá que configurarse con la clave pública y privada del servidor para que pueda descifrar las solicitudes de procesamiento.

Consulte la documentación de su equilibrador de carga preferido para averiguar cómo configurarlo para controlar las solicitudes HTTP/2 con los servicios back-end.

## <a name="load-balancing-within-kubernetes"></a>Equilibrio de carga dentro de Kubernetes

Consulte [la sección sobre las mallas de servicio](service-mesh.md) para obtener una explicación del equilibrio de carga entre servicios internos en Kubernetes.

>[!div class="step-by-step"]
>[Anterior](service-mesh.md)
>[Siguiente](application-performance-management.md)
