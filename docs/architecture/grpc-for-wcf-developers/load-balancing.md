---
title: Equilibrio de carga gRPC-gRPC para desarrolladores de WCF
description: Elección de un equilibrador de carga para trabajar con gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711174"
---
# <a name="load-balancing-grpc"></a>Equilibrio de carga gRPC

Una implementación típica de una aplicación de gRPC incluye varias instancias idénticas del servicio, lo que proporciona resistencia y escalabilidad horizontal. El equilibrio de carga distribuye las solicitudes entrantes entre estas instancias para proporcionar el uso completo de todos los recursos disponibles. Para que este equilibrio de carga sea invisible para el cliente, es habitual usar un servidor de equilibrador de carga de proxy para controlar las solicitudes de los clientes y enrutarlas a las instancias de back-end.

Los equilibradores de carga se clasifican según la *capa* en la que operan. Los equilibradores de carga de nivel 4 funcionan en el nivel de *transporte* , por ejemplo, con Sockets TCP, conexiones y paquetes. Los equilibradores de carga de nivel 7 funcionan en el nivel de *aplicación* , y controlan específicamente las solicitudes HTTP/2 para las aplicaciones gRPC.

## <a name="l4-load-balancers"></a>Equilibradores de carga L4

Un equilibrador de carga L4 acepta una solicitud de conexión TCP de un cliente, abre otra conexión a una de las instancias de back-end y copia los datos entre las dos conexiones sin ningún procesamiento real. L4 ofrece un rendimiento excelente y una baja latencia, pero muy poco control o inteligencia. Siempre que el cliente mantenga abierta la conexión, todas las solicitudes se dirigirán a la misma instancia de back-end.

 [Azure load balancer](https://azure.microsoft.com/services/load-balancer/) es un ejemplo de un equilibrador de carga L4.

## <a name="l7-load-balancers"></a>Equilibradores de carga L7

Un equilibrador de carga L7 analiza las solicitudes HTTP/2 entrantes y las pasa a las instancias de back-end de manera solicitada, independientemente de cuánto tiempo tenga la conexión el cliente.

Ejemplos de equilibradores de carga L7:

- [NGINX](https://www.nginx.com/)
- [HAProxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Como regla general, los equilibradores de carga L7 son la mejor opción para gRPC y otras aplicaciones HTTP/2 (y, por lo general, para las aplicaciones HTTP). Los equilibradores de carga L4 *funcionarán* con las aplicaciones de gRPC, pero son especialmente útiles cuando es importante una latencia baja y una sobrecarga baja.

> [!IMPORTANT]
> En el momento de redactar este documento, algunos equilibradores de carga L7 no admiten todas las partes de la especificación HTTP/2 que requieren los servicios de gRPC, como los encabezados finales.

Si usa el cifrado TLS, los equilibradores de carga pueden finalizar la conexión TLS y pasar las solicitudes no cifradas a la aplicación back-end, o bien pueden pasar la solicitud cifrada. En cualquier caso, el equilibrador de carga tendrá que configurarse con la clave pública y privada del servidor para que pueda descifrar las solicitudes de procesamiento.

Consulte la documentación de su equilibrador de carga preferido para averiguar cómo configurarlo para controlar las solicitudes HTTP/2 con los servicios back-end.

## <a name="load-balancing-within-kubernetes"></a>Equilibrio de carga dentro de Kubernetes

Consulte [la sección sobre las mallas de servicio](service-mesh.md) para obtener una explicación del equilibrio de carga entre servicios internos en Kubernetes.

>[!div class="step-by-step"]
>[Anterior](service-mesh.md)
>[Siguiente](application-performance-management.md)
