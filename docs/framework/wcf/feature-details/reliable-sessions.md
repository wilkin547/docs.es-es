---
description: 'Más información acerca de: sesiones confiables'
title: Sesiones de confianza
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 86df4ccf9c1fd52d162ad7272ece5591f0ca7482
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632885"
---
# <a name="reliable-sessions"></a>Sesiones de confianza

En esta sección se describe qué es una sesión confiable de Windows Communication Foundation (WCF), para qué se usa, cómo y Cuándo usar una, qué configuraciones de enlace lo admiten y punteros en procedimientos recomendados. La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.

WCF de sesión confiable proporciona características que garantizan que los mensajes enviados entre los puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en el que se enviaron.

Para utilizar una sesión confiable con una aplicación WCF, use uno de los enlaces proporcionados por el sistema en WCF que admitan una sesión confiable de forma predeterminada o como opción, o bien cree su propio enlace personalizado que admita la sesión.

## <a name="in-this-section"></a>En esta sección

[Información general de sesiones confiables](reliable-sessions-overview.md) Describe las sesiones confiables, Cuándo utilizarlas, los distintos enlaces que admiten sesiones confiables y cómo funcionan.

[Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md) Describe cómo crear una sesión confiable sobre HTTP mediante un enlace personalizado especificado en la configuración.

[Cómo: proteger mensajes dentro de sesiones confiables](how-to-secure-messages-within-reliable-sessions.md) Describe cómo proteger una sesión confiable.

[Cómo: crear un enlace de sesión confiable personalizado con https](how-to-create-a-custom-reliable-session-binding-with-https.md) Describe cómo crear una sesión confiable sobre HTTPS.

[Prácticas recomendadas para sesiones confiables](best-practices-for-reliable-sessions.md) Describe algunas de las prácticas recomendadas asociadas con el uso de una sesión confiable.

## <a name="reference"></a>Referencia

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vea también

- [Colas y sesiones de confianza](queues-and-reliable-sessions.md)
- [Sesiones, creación de instancias y simultaneidad](sessions-instancing-and-concurrency.md)
